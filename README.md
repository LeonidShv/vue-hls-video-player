# vue-hls-video-player

## Descriptions

It is a video player for the m3u8 format

Requirements:
  only for the vue 3 projects

## Examples, how to use component
```
<VideoPlayer
    type="default"
    @pause="processPause"
    previewImageLink="poster.webp"
    link="videoLink.m3u8"
    :progress="30"
    class="customClassName"
/>

 <VideoPlayer
    type="preview"
    previewImageLink="poster.webp"
    link="videoLink.m3u8"
    class="customClassName"
/>
```
