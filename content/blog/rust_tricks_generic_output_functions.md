---
title: "rust_tricks_generic_output_functions"
date: 2023-10-30T22:02:05+01:00
draft: false
---

I'm re-writing my [network-delay-differential-equations-solver](https://github.com/exo-cortex/dynamical_system_in_rust) from my master thesis --- this time in Rust (of course!). The idea is to learn more about the language. That's why I try to tackle problems by using clever new approaches that Rust enables me to do. 
Along the way I there've been a few tricks that I learned or that nice people taught me which made it or will make it into the program. This one came from a friend who's much more experienced in such things:

# Neat trick #1

So --- I have a struct that is holding some data. As the structs data changes over time I want to keep either (**a**) ***all***, (**b**) ***some*** of its data, (**c**) new data ***derived*** from the struct's data or (**d**) a ***combination*** of (**a-c**). So I have my struct `Data` and I need a way to have multiple `get_data()`-functions that return it in various ways (**a** - **c**):

```rust
// all the structs fields and output types are `f32` which is a random choice.
struct Data {
    x: f32,
    y: f32,
    z: f32,
}

fn get_data_a(d: &Data) -> [f32; 3] {
    [d.x, d.y, d.z] // (a) all of `Data`
}
fn get_data_b_z(d: &Data) -> [f32; 1] {
    [d.z] // (b) some of `Data` - in this case only `z` 
}
fn get_data_c_1(d: &Data) -> [f32; 1] {
    [d.x.sqrt()] // (c) values derived through transforming `x`` 
}
fn get_data_d_1(d: &Data) -> [f32; 4] {
    [d.x, d.x * d.y, d.y - d.z, d.z.sqrt()] // (d) some combination of the above
}
```

If needed I can define a large number of these `get_data_*()`-functions - I just need to pic a name and then I can call them from somewhere else.

But now I need to have multiple such `Data`-types that each have their own little zoo of `get_data_*()`-functions. Each is defined as a separate module:

```rust
mod CoolData {
    struct Data { /* data */ }
    fn get_data_1(d: &Data) -> [f32; n_1]
    // ...
    fn get_data_N(d: &Data) -> [f32; n_N]
}

mod HappyData {
    struct Data { /* data */ }
    fn get_data_1(d: &Data) -> [f32; m_1]
    // ...
    fn get_data_M(d: &Data) -> [f32; m_M]
}

// ... and so son
```
Somewhere else I want to write functions generically for all of my `Data`-types and use their `get_data_*()`-functions. The way to do it is to define a trait e.g. `DataHolder` that each `Data` has to implement in order to use these functions. Easy, that's how Rust's traits work.

But how can I use the `get_data_*()`-functions if each of these modules has a different number of `get_data_*()` and each have a different return-type? If I have all the `get_data_*()`'s in the trait `DataHolder` across all modules we have to have the same number of these functions and each of them has to have the same return type. That's very impractical. 

The solution is to define a different helper-type `As*` that only holds a reference to `Data` for each `get_data_*()` and a (const-)generic trait `get_data<const N: usize>` that each helper-type has to implement.
```rust 
struct Data { x: f32 }

pub trait GiveSomeData<const N: usize> {
    fn get_data(&self) -> [f32; N];
}

struct AsA<'a>(&'a Data);
impl<'a> GiveSomeData<1> for AsA<'a> {
    fn get_data(&self) -> [f32; 1] {
        [self.0.x]
    }
}

struct AsB<'a>(&'a Data);
impl<'a> GiveSomeData<4> for AsB<'a> {
    fn get_data(&self) -> [f32; 4] {
        [self.0.x, self.0.x.sqrt(), self.0.x.exp(), self.0.x.sin()] // for example
    }
}

// use these 
pub fn use_data<const N: usize, T: GiveSomeData<T>>(d: &T) {
    println("{:?}", t.get_data());
}
```
voilà: Now each module can have their own set of various output formats and transformations that still adhere to a common interface. 

My version will likely also have a second method required by `GiveSomeData<N>` that returns a `&'static [&'static]` in which each `get_data_*()`'s output array's elements are described e.g. for `AsB` from above:

```rust
impl<'a> GiveSomeData<4> for AsB<'a> {
    fn get_data(&self) -> [f32; 4] { /* see above */ };
    fn get_data_descriptions() -> &'static [&'static str] {
        ["x", "sqrt_of_x", "exp_of_x", "sine_of_x"]
    }
}
```
When writing each element of the the output array into a separate fil these files will be named according to `get_data_descriptions()`'s output elements.

Now in my usecase these `get_data_*()`'s will be called _all the time_, so they have to be fast and ideally should be optimized at compile time. So I need to tell the compiler to have each of them ready. I likely need a `match` that automatically adds arms for each existing `get_data_*()`. Likely I need a macro. But that is a tale for another time...