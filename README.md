# spotify-videos

A web application (currently in early development) that connects to a Spotify Premium account and plays corresponding music videos using an [Invidious](https://github.com/iv-org/invidious) instance. It fetches videos from YouTube, but leverages the Invidious front-end to bypass copyright restrictions and API quota limitations imposed by YouTube.

## About

This project was originally created for small events, allowing a laptop to connect to a video projector and automatically play music videos for guests to enjoy and dance to.

## Usage

Although still under development and potentially buggy, the app is functional and can be tested at:

[rossi.nz/mine/spotify-videos](https://rossi.nz/mine/spotify-videos/)

### Steps:

1. Sign in with your Spotify Premium account.
2. Host an Invidious instance locally. [Read the documentation](https://invidious.io/)
3. The app will attempt to detect Invidious running at [localhost:3000](http://localhost:3000)
4. Ensure autoplay is enabled for both audio and video in your browser.
5. Music videos should begin playing automatically.

### Tips:

- Click the track title to toggle between the music video and cover art.
- Cover art will display automatically if Spotify or Invidious is unavailable.
- Press **S** to toggle the upcoming settings panel.
- Press **O** to switch between cover art and music video views.

## How It Works

1. The app polls the Spotify API every 3 seconds to check the currently playing track.
2. It queries the Invidious API with the format: `track - artist official music video`.
3. It retrieves and embeds the video using the corresponding video ID.
4. If Invidious is unavailable or disabled by the user, the app will fallback to Spotify cover art.
5. If neither Spotify nor Invidious responds, the screen will remain blank.
6. All activity and errors are logged in the browser console.

## Planned Features

- **Settings Page**  
  Customize your Invidious instance URL, video query format, and more.

- **Video Syncing**  
  Sync video playback with Spotify — including pausing when Spotify pauses.

- **Expanded Service Support**  
  Add support for Deezer, Apple Music, YouTube Music, and custom APIs.

- **Remote Control Panel**  
  Manage playback remotely without touching the device running the app.
