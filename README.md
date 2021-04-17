# Nowify

A simple app to display your currently playing Spotify track on a Raspberry Pi, made with Vue.

Nowify will:

* ✅ - Use Spotify Web API to get your current track
* ✅ - Only access that and no other data
* ✅ - Use Access and Refresh Tokens to ensure that you;re kept logged in between sessions
* ✅ - Display the current track artist, cover, and a matching vibrant background colour

Preview:
![Nowify Preview Image 1](assets/preview-1.png?raw=true "Nowify preview image, cover art for the song 'Wherever you go' by The Avalanches and Jamie xx")
![Nowify Preview Image 2](assets/preview-2.png?raw=true "Nowify preview image, cover art for the song 'Gas Drawls' by MF DOOM")
![Nowify Preview Image 3](assets/preview-3.png?raw=true "Nowify preview image, cover art for the song '有吗炒面' by Lexie Liu")
---

Original Write up:
[https://ashcroft.dev/blog/now-playing-screen-spotify-raspberry-pi-es6/](https://ashcroft.dev/blog/now-playing-screen-spotify-raspberry-pi-es6/)

## How to use:
To use this, you'll need to clone the repo, generate some API keys and run some commands to compile the code.

To compile the code, you will need a package manager installed. Either [npm](https://www.npmjs.com/get-npm) or [yarn](https://classic.yarnpkg.com/en/docs/install/#mac-stable). I use yarn.

1. Create Spotify Client keys.
To allow authorisation to your track data, you'll need to generate client keys. You can do this by logging in to the [Spotify Dashboard](https://developer.spotify.com/dashboard/applications) creating an app.

2. Clone this repository and install dependencies
After you clone, navigate to the directory and install the dependencies:

via yarn:
```
yarn install
```

via npm:
```
npm install
```

3. Add your Client ID and Client Secret
Copy the `.env.sample` file to a new file called `.env` and enter your generated Client ID and Client Secret.

4. Compile the code
In the repo directory, run the following command to compile the project:

via yarn:
```
yarn build
```

via npm:
```
npm run build
```

You can also run the development version locally on your machine:

via yarn:
```
yarn serve
```

via npm:
```
npm run serve
```

5. Upload to a webserver.
The output of `yarn build` will be created in a folder called `/dist/` - this is the usable version of Nowify which is ready to be added to your web server. You could use Netlify, GitHub Pages, Vercel, or any webserver for this. I use Netlify.

Alternatively, you can use packages to run a local webserver.

*NOTE*: This app uses Environment Variables to keep your Client ID and Secret secure. These will not be added to your

6. View on your Pi and play some music.
Now you're ready to go. Open your site on the Raspberry Pi, login, and play some music. I'd recommend disabling the screensaver on your Pi and opening Chromium in kiosk mode:

```
@xset s off # disable the screensaver
@xset -dpms # disable energy saving features
@xset s noblank # ensure screen doesn't go blank
DISPLAY=:0 chromium-browser -kiosk https://[your-url] # open up chromium to specific web page
```
---
### Original Write up:
[https://ashcroft.dev/blog/now-playing-screen-spotify-raspberry-pi-es6/](https://ashcroft.dev/blog/now-playing-screen-spotify-raspberry-pi-es6/)

### Brief About:
Nowify was a project that I originally made in 2017 when I wanted to learn more modern Javascript. Over the years, I've learned a lot more and had people contact me about Nowify, so I wanted to build a more modern version of it using modern tools. This is still a learning exercise, but hopefully one that's more usable. If you'd like to view the old repository, that can be found on the `old` branch.