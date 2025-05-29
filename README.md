# Using getDisplayMedia to record the screen, system or browser tab audio, and the microphone

The code in this repo, [available here as a live demo](https://addpipe.com/get-display-media-demo/), uses `getDisplayMedia()` and the `MediaStream Recording API` to record the screen, your microphone & system or tab audio.

When you click the Share Screen button, Chrome and Chromium based browsers may also offer the option to include system or tab audio on supported operating systems (see below).

To ensure both microphone and system audio are included in the final recording, the demo uses the [Web Audio API](https://developer.mozilla.org/en-US/docs/Web/API/Web_Audio_API) to combine the two audio sources in real time. The microphone stream is captured using `getUserMedia()`, while the system or tab audio is captured as part of the screen stream via `getDisplayMedia()`. These two audio tracks are mixed together and merged with the video track into a single stream. This composed stream is then passed to a `MediaRecorder` object, which produces a single `.webm` file containing your screen video, microphone input, and system or tab audio, if available.

## Requirements

### `getDisplayMedia` requirements:
* Chrome 72 and above  (system and tab audio in Chrome 74+ on supported operating systems, see below)
* Edge 79 and above
* Firefox 66 and above
* Opera 60 and above
* Safari 13 and above

### Capturing system or tab audio requirements:
* Capturing system audio is possible on Chrome 74+ (and other Chromium based browsers like Edge and Opera) on Windows and ChromeOS when sharing the entire screen, and the user needs to opt in
* Capturing tab audio is possible on Chrome 74+ (and other Chromium based browsers like Edge and Opera) on macOS, Windows, Linux and ChromeOS when sharing a browser tab, and the option is preselected

## Links:
* [Live demo of this code](https://addpipe.com/get-display-media-demo/)
* [Screen Capture W3C Working Draft](https://www.w3.org/TR/screen-capture/)
* [Chrome Tutorial: Recording The Screen With Both Microphone Audio AND System Sounds](https://blog.addpipe.com/recording-the-screen-in-chrome-with-both-microphone-audio-and-system-sounds/)
* [Product Announcement: Screen Recording With System Sounds In the Pipe Recording Client](https://blog.addpipe.com/screen-recording-with-system-sounds-in-chrome/)
