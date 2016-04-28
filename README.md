## soundcloud-audio-interface

provides an HTMLAudioElement and a MediaElementAudioSourceNode for a soundcloud track, given a url and a client id

### install

`npm i --save soundcloud-audio-interface`

### usage

```js
import SoundcloudAudioInterface from 'soundcloud-audio-interface'

var audioCtx = new (window.AudioContext || window.webkitAudioContext)()
var audioOut = audioCtx.destination

var scAudioInterface = new SoundcloudAudioInterface({
  audioCtx: audioCtx,
  clientId: YOUR_SC_CLIENT_ID
})

scAudioInterface.setUrl(url)
  .then(() => {
    scAudioInterface.source.connect(audioOut)
    scAudioInterface.audio.play()
  }).fail((reason) => {
    console.log('failed with error: ', reason)
  })
```
