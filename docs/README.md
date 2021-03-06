# Hello!

**indigo-player** is an **extensible**, **modern**, JavaScript player. With our module system, it's childsplay for developers to add their own logic. Whether it's ads, custom business rules or supporting a new stream format, this documentation should get you started in no time.

## Hosting

* jsdelivr.net: https://cdn.jsdelivr.net/npm/indigo-player/lib/indigo-player.js
* by using your own host:
  * 1) Let's say you host it at *https://mysite.com/js/indigo-player.js*,
  * 2) Make sure you set *IndigoPlayer.setChunksPath('https://mysite.com/js/')** before calling `init(...)` as the chunks path.

## Basic example

The example below will load a simple MP4 file, and attempt to autoplay it. In order to interact with the player, you can use the `player` object returned when initializing indigo-player.

```javascript
<html>
  <body>
    <div id="playerContainer"></div>
    <script src="https://cdn.jsdelivr.net/npm/indigo-player@1/lib/indigo-player.js"></script>
    <script>
      const config = {
        ui: true,
        sources: [
          {
            type: 'mp4',
            src: 'https://commondatastorage.googleapis.com/gtv-videos-bucket/sample/BigBuckBunny.mp4',
          }
        ],
      };

      const element = document.getElementById('playerContainer');
      const player = IndigoPlayer.init(element, config);
    </script>
  </body>
</html>
```

<div class="sample-player" data-expose-player="player">
{
  ui: true,
  sources: [
    {
      type: 'mp4',
      src: 'https://commondatastorage.googleapis.com/gtv-videos-bucket/sample/BigBuckBunny.mp4',
    },
  ],
}
</div>

?> Open up the console, and use `window.player` to interact with the player above.

<iframe style="margin: 0; border: 0;" src="https://ghbtns.com/github-btn.html?user=matvp91&repo=indigo-player&type=star&count=true&size=medium" frameborder="0" scrolling="0" width="160px" height="30px"></iframe>


## Features

* **media** - mp4
* **media** - Dash (+ DRM / Widevine & PlayReady) - *shaka-player*
* **media** - HLS - *hls.js*
* **media** - Native HLS (+ FairPlay) - *work in progress*
* **player** - HTML5 video element
* **ads** - FreeWheel (client-side)
* **ads** - Google IMA (client-side)

## Supported browsers

* Chrome 71+
* Firefox 64+
* Edge 44+ on Windows 10
* IE11 on Windows 7 except for DRM content

Previous browser versions will most likely work because we rely heavily on feature detection based on the given configuration.