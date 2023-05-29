# vue-hls-video-player

## Descriptions

It is a video player for the **m3u8** format

Requirements:
  only for the **vue 3** projects

## Examples, how to use component
```
npm i vue-hls-video-player

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

## Props:
**type**: 
1. default - default video player, where you can process pauses and setup progress time
2. preview - you can pause video on hover

**@pause**: 
1. event how you can process pauses 
@pause="processPause"
```
function processPause(progress: number) {
  console.log(progress)
}
```
**previewImageLink**: 
preview (poster) image for the video player

**link**: 
link on video.m3u8

## Aditional information
If you have any ideas, or need a fast fix, write me and I try to help you
1. [GitHub](https://github.com/LeonidShv/vue-hls-video-player)
2. [npm](https://www.npmjs.com/package/vue-hls-video-player?activeTab=readme)
3. [Linkedin](https://www.linkedin.com/in/leonid-shvab-a2a32b1a7/)
4. [Portfolio](https://leonid-shvab.web.app/)