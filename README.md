# @plantquest/assetmap

> [![npm version](https://img.shields.io/npm/v/@plantquest/assetmap.svg)](https://www.npmjs.com/package/@plantquest/assetmap)

![Logo_Plantquest_horizontal](https://user-images.githubusercontent.com/89012461/223706137-a9682633-cebb-47ab-8bdf-0452e6b7fff4.png)
>PlantQuest is a supplier of asset mapping solutions to the Life Science sector. The industry focused PlantQuest Asset Map allows users to intergrate the PlantQuest mapping technology into their technology stack. Upon doing so, users can manipulate maps and display asset information within the context of where it is generated helping workers to make smarter, quicker and more insightful decisions. In turn, increasing their operational effeciency.

## Install

```bash
npm install --save @plantquest/assetmap
```

## Usage



## Debug Log

Set `window.PLANTQUEST_ASSETMAP_LOG` to `true` to enable logging.


## Options

* `width`: Pixel width of map
* `height`: Pixel height of map
* `mapBounds`: Pixel bounds of map
* `mapStart`: Pixel start position of map
* `mapStartZoom`: Starting zoom level
* `mapRoomFocusZoom`: Zoom level for room focus
* `mapMaxZoom`: Maximum zoom
* `mapMinZoom`: Minimum zoom
* `states`: State definitions
  * `{ [stateName]: { color: COLOR, name: STRING, marker: 'standard'|'alert'}, ...}`
* `start.map`: Starting map
* `start.level`: Starting level
* `room.color`: Room highlight color


## Messages

  <h2>SEND MESSAGES</h2>

  <h3>ZOOM</h3>
  <pre>
    {
      srv: 'plantquest',
      part: 'assetmap',
      ZOOM: &lt;INTEGER&gt;,     
    }
  </pre>
  <p>Where:<br>
    <i>&lt;INTEGER&gt;</i>: Zoom level (default: -4 to +2)<br>
  </p>


  <h3>GET RELATION</h3>
  <pre>
    {
      srv: 'plantquest',
      part: 'assetmap',
      relate: 'room-asset',
    }
  </pre>
  <p>Listen: <a href="#listen-relation">RELATION</a><br>
  </p>


  <h3>SHOW ROOM</h3>
  <pre>
    {
      srv: 'plantquest',
      part: 'assetmap',
      show: 'room',
      room: &lt;ROOM-ID&gt;,     
    }
  </pre>
  <p>Where:<br>
    <i>&lt;ROOM-ID&gt;</i>: Room Identifier String<br>
  </p>


  <h3>SET ASSET STATUS</h3>
  <pre>
    {
      srv: 'plantquest',
      part: 'assetmap',
      status: &lt;STATUS&gt;,
      asset: &lt;ASSET-ID&gt;,     
    }
  </pre>
  <p>Where:<br>
    <i>&lt;STATUS&gt;</i>: Status String ('red', 'green')<br>
    <i>&lt;ASSET-ID&gt;</i>: Asset Identifier String<br>
  </p>

  
  
  <h2>LISTEN MESSAGES</h2>
   
  <h3>STATE</h3>
  <pre>
    {
      srv: 'plantquest',
      part: 'assetmap',
      state: &lt;STATE&gt;,
    }
  </pre>
  <p>Where:<br>
    <i>&lt;STATE&gt;</i>: 'ready'<br>
  </p>


  <a name="listen-relation"></a>
  <h3>RELATION</h3>
  <pre>
    {
      srv: 'plantquest',
      part: 'assetmap',
      relate: 'room-asset',
      relation: &lt;RELATION&gt;,
    }
  </pre>
  <p>Where:<br>
    <i>&lt;RELATION&gt;</i>:
    <pre>
      { '&lt;ROOM-ID&gt;': [ '&lt;ASSET-ID&gt;', ... ] }
    </pre>
    <br>
  </p>


  <h3>USER SELECT ROOM</h3>
  <pre>
    {
      srv: 'plantquest',
      part: 'assetmap',
      select: 'room',
      room: &lt;ROOM-ID&gt;,     
    }
  </pre>
  <p>Where:<br>
    <i>&lt;ROOM-ID&gt;</i>: Room Identifier String<br>
  </p>



## Licenses

[MIT](LICENSE) © [Plantquest Ltd](https://plantquest.com)
[BSD 2-Clause](LEAFLET-LICENSE) © [Vladimir Agafonkin, Cloudmade](https://leafletjs.com/)
[MIT](LICENSE) © [Justin Manley](https://github.com/Leaflet/Leaflet.toolbar)
