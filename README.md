# Teleprompter

A teleprompter for iPhone that shows your script over the live front-camera
picture while you record. The text sits at the top of the screen, next to the
lens, so you look at your audience instead of off to the side. The script is
only on screen; it is never part of the recorded video.

It is a web app with no build step and no dependencies: `index.html` holds the
whole app.

## How it works on iPhone

iOS does not let any app draw on top of the built-in Camera app, so this app
does the recording itself: it opens the front camera, records video and sound,
and shows the script on top of the preview.

1. Open the app's **https** address in Safari and allow camera and microphone.
2. Tap **Share → Add to Home Screen** to run it full screen like a normal app.
3. Tap **Script** and type or paste your text.
4. Tap the red button. After the countdown, recording and scrolling start together.
5. Tap stop, then **Save video → Save Video** to put the take in Photos.

While reading:

- Tap the text to pause or resume scrolling; drag it to move back or ahead.
- **−** / **+** change the pace in words per minute.
- **Settings** has text size, prompter height, background dim, countdown,
  front/back camera and video quality.

Your script and settings are stored on the phone only. Nothing is uploaded.

## Hosting it

The camera needs a secure page, so the files must be served over https.
With GitHub Pages: **Settings → Pages → Deploy from a branch**, pick the branch
and the `/ (root)` folder. The app is then at
`https://<user>.github.io/<repo>/`.

## Running locally

```sh
python3 -m http.server 8000
```

`http://localhost:8000` works on the same computer. A phone on your Wi-Fi needs
https, so use GitHub Pages or an https tunnel for that.

## Requirements

iOS 14.3 or later (Safari). Also works in current Chrome, Edge and Firefox.
