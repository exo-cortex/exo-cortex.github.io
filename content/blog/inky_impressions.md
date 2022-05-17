---
title: "new toy: 7-color e-ink display"
date: 2021-12-06T12:03:09+01:00
update: 2022-05-17T12:02:00
draft: false
tags: [raspberry pi, e-ink, pimorony, art]
---


After considerable to and fro I finally ordered a 7-color e-ink [^1] display for the raspberry pi from pimoroni [^2]. With the help of the official repository [^3] putting images on the the display is quite easy. The repository also has code for other e-ink-displays from pimoroni. 

{{<figure src="/img/inky_paris_1.jpg" title="inky impressions display showing a photograph of paris">}}

With about 85mm x 115mm it is comparable to typical e-reader display sizes. Although the glass leads to a different look compare to the matte e-reader displays. When setting a new image the transition looks quite elaborate and takes about 30 seconds of flashing through different colors. Eventually it looks quite interesting. With the limited range of colors everything looks a little like an art print with intentionally noticeable dithering artifacts [^4]. The artifacts are shown in the closeups beneath.

{{<figure src="/img/inky_paris_2.jpg" title="a closup of the image">}}
{{<figure src="/img/inky_paris_3.jpg" title="even closer closup">}}


# update: e-paper display in a frame
After ordering a paper mat[^5] and frame of fitting size for the display I *finally* went on and build a fixure so that the display would stay at the right position behind the opening.  I used 3mm gray paperboard and cut it to size. 
{{<figure src="/img/inky_frame_fixture_1_small.jpg" title="lalala">}}
{{<figure src="/img/inky_frame_fixture_2_small.jpg" title="lalala">}}

The framed display already aced its first test passing as a regular paper print, when my girlfriend didn't notice anything about it.

**next up**:
writing some scripts that automatically resize, crop and put images onto the display. Also some scripts that show weather information.

[^1]: https://en.wikipedia.org/wiki/Electronic_paper
[^2]: https://shop.pimoroni.com/products/inky-impression
[^3]: https://github.com/pimoroni/inky
[^4]: https://en.wikipedia.org/wiki/Dither
[^5]: https://en.wikipedia.org/wiki/Mat_(picture_framing) (in German: "passepartout")