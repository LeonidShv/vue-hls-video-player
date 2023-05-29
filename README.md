# vue-hls-video-player

### Descriptions

It is a video player for the **m3u8** format

Requirements:
  only for the **vue 3** projects

### Examples, how to use component
```
npm i vue-hls-video-player

<VideoPlayer
    type="default"
    @pause="processPause"
    previewImageLink="poster.webp"
    link="videoLink.m3u8"
    :progress="30"
    :isMuted="false"
    :isControls="true"
    class="customClassName"
/>

 <VideoPlayer
    type="preview"
    previewImageLink="poster.webp"
    link="videoLink.m3u8"
    class="customClassName"
/>
```

### Props:
**type**: 
1. value: 'default', type: String

default video player, where you can process pauses and setup progress time.

Default props for the **type: default**:
```
:isMuted="false"
:isControls="true"
```
2. value: 'preview', type: String

you can pause video on hover, without sound (muted), without controls. It does not have access to props: isMuted, isControls, progress, @pause

Default props for the **type: preview**:
```
:isMuted="true"
:isControls="false"
```

**@pause**: 
1. Event, for processing pauses:
@pause="processPause"
```
function processPause(progress: number) {
  console.log(progress)
}
```
**previewImageLink**: 
1. value: 'poster.webp', type: String

poster image for the video player

**link**: 
1. value: 'videoLink.m3u8', type: String

link on video in format m3u8

**isMuted**:
1. value: true or false, type: Boolean

it can turn on and off the sound of the video

**isControls**:
1. value: true or false, type: Boolean

it can show and hide the video control panel
### Aditional information
If you have any ideas, or need a fast fix, write me and I try to help you
1. [GitHub](https://github.com/LeonidShv/vue-hls-video-player)
2. [npm](https://www.npmjs.com/package/vue-hls-video-player?activeTab=readme)
3. [Linkedin](https://www.linkedin.com/in/leonid-shvab-a2a32b1a7/)
4. [Portfolio](https://leonid-shvab.web.app/)