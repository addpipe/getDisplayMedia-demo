# Using getDisplayMedia to record the screen

[This demo](https://addpipe.com/get-display-media-demo/) uses `getDisplayMedia()` and the `Media Stream Recording API` to record the screen, your microphone & system audio on Chrome.

When you click the “Share Screen” button, the browser may also offer the option to include system or tab audio. This is supported in browsers like Chrome. If you select that option, the demo captures the system audio directly from the screen stream.

To ensure both microphone and system audio are included in the final recording, the demo uses the [Web Audio API](https://developer.mozilla.org/en-US/docs/Web/API/Web_Audio_API) to combine the two audio sources in real-time. The microphone stream is captured using `getUserMedia()`, while the system audio is captured as part of the screen stream via `getDisplayMedia()`. These two audio tracks are mixed together and merged with the video track into a single stream. This composed stream is then passed to the `MediaRecorder`, which produces a single `.webm` file containing your screen video, microphone input, and system or tab audio, if available.

Works on:
* Chrome 72 and above (with system/tab audio)
* Edge 79 and above
* Firefox 66 and above
* Opera 60 and above

Limitations:
* Sharing the system audio is only possible on Chrome on Windows, and the user needs to opt in
* Sharing tab audio is possible on Chrome on macOS, Windows, and the option is preselected
* Firefox and Safari do not support capturing system sounds or tab audio

Links:
* [Live demo of this code](https://addpipe.com/get-display-media-demo/)
* [W3C Spec](https://www.w3.org/TR/screen-capture/)
* [Blog post](https://blog.addpipe.com/screen-recording-with-system-sounds-in-chrome/)
