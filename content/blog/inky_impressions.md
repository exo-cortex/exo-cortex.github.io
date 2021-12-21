---
title: "new toy: 7-color e-ink display"
date: 2021-12-06T12:03:09+01:00
draft: false
tags: [raspberry pi, e-ink, pimorony, art]
---


After considerable to and fro I finally ordered a 7-color e-ink [^1] display for the raspberry pi from pimoroni [^2]. With the help of the official repository [^3] putting images on the the display is quite easy. The repository also has code for other e-ink-displays from pimoroni. 

{{<figure src="/img/inky_paris_1.jpg" title="inky impressions display showing a photograph of paris">}}

With about 85mm x 115mm it is comparable to typical e-reader display sizes. Although the glass leads to a different look compare to the matte e-reader displays. When setting a new image the transition looks quite elaborate and takes about 30 seconds of flashing through different colors. Eventually it looks quite interesting. With the limited range of colors everything looks a little like an art print with intentionally noticeable dithering artifacts [^4]. The artifacts are shown in the closeups beneath.

{{<figure src="/img/inky_paris_2.jpg" title="a closup of the image">}}
{{<figure src="/img/inky_paris_3.jpg" title="even closer closup">}}

# plans for the display
One thing I want do is put the display in a nice frame with a perfect-fit fine paper mat [^5]. Ideally the mat makes the display look like regular paper. Then it would appear like a regular art piece that surprises people when it shows different images at different times.

Furthermore I want to check out the code from the repository a bit more and see how and when dithering is applied. I like the look of dither quite a bit, although it fits less for images related to pixel art. As the display applies dither on default I have to make images that only use the 7 primary colors of the image. This blog post will be updated. With new images.

[^1]: https://en.wikipedia.org/wiki/Electronic_paper
[^2]: https://shop.pimoroni.com/products/inky-impression
[^3]: https://github.com/pimoroni/inky
[^4]: https://en.wikipedia.org/wiki/Dither
[^5]: https://en.wikipedia.org/wiki/Mat_(picture_framing) (in German: "passepartout")