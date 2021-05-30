---
title: "ffmpeg_scripts"
date: 2021-05-30T20:09:19+02:00
draft: false
---

How to use ffmpeg. 
I use ffmpeg to convert videos from one format to the other. In order to create small video files from gifs I use this script:

```bash
#!/usr/bin/sh
# two-pass video-conversion with resizing to width 
echo "$1 >> $2 resizing to width=$3 with target video-bitrate of $4"

ffmpeg -y -i "$1" -vf scale=$3:-1 -c:v vp9 -preset quality -b:v $4 -pass 1 -an -auto-alt-ref 0 -f webm /dev/null && \
ffmpeg -i "$1" -vf scale=$3:-1 -c:v vp9 -preset quality -b:v $4 -pass 2 -an -auto-alt-ref 0 $2
```
explanation: 

- an -> drop audio
- vf -> video filtering
- c:v -> video codec - here "vp9"
- preset -> [ultrafast, superfast, veryfast, faster, fast, medium (default), slow, slower, veryslow] 