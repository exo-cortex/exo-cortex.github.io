---
title: "ffmpeg_scripts"
date: 2021-05-30T20:09:19+02:00
draft: false
tags: [ffmpeg, help, how-to]
---

using ffmpeg. 
I use ffmpeg to convert videos from one format to the other. In order to create small video files from gifs I use this script:

```bash
#!/usr/bin/sh
# two-pass video-conversion with resizing to width 
echo "$1 >> $2 resizing to width=$3 with target video-bitrate of $4"

ffmpeg -y -i "$1" -vf scale=$3:-1 -c:v vp9 -preset quality -b:v $4 -pass 1 -an -auto-alt-ref 0 -f webm /dev/null && \
ffmpeg -i "$1" -vf scale=$3:-1 -c:v vp9 -preset quality -b:v $4 -pass 2 -an -auto-alt-ref 0 $2
```

## explanation
- -an (no audio)
- -vf (video filtering -> see below)
- -c:v (video codec options - e.g. **vp9** or **libx264** )
- -c:a (audio codec - e.g. **vorbis**)
- -preset ([ultrafast, superfast, veryfast, faster, fast, medium (default), slow, slower, veryslow])
- -b:v 1M (video bitrate )
- -b:a (audio bitrate)

## [*] some video filter options
- scale=400:-1 (resize to width=400, keep aspect ratio)
- scale=iw/2:-1 (resize image to 50% of input_width resolution, might stretch/squash the image)
- scale=400:300 (resize image to 400x300 resolution, might stretch/squash the image)
- negate (invert colors)

## other useful command: 
- -codecs (print out a list of all codecs available on this computer) 

---
links:
- [ffmpeg documentation](https://ffmpeg.org/documentation.html)
- [vp9 guide](https://trac.ffmpeg.org/wiki/Encode/VP9)
- [h264 guide](https://trac.ffmpeg.org/wiki/Encode/H.264)
- [av1guide](https://trac.ffmpeg.org/wiki/Encode/AV1)
- [filtering guide](https://trac.ffmpeg.org/wiki/FilteringGuide)
- [list avaliable codecs](https://write.corbpie.com/ffmpeg-list-all-codecs-encoders-decoders-and-formats/)