
---

# JioSaavn Plugin (Kazagumo)

A JioSaavn plugin for the Kazagumo module.
**Note:** This plugin only supports ESM. CommonJS and TypeScript are not supported at the moment (support may be added if published to npm).

---

## Accepted Query Types

```
Song link:     https://jiosaavn.com/song/excuses/BFUIPyJ0BGY  
Album link:    https://jiosaavn.com/album/say-my-name/PycbDgPUyPU  
Playlist link: https://jiosaavn.com/featured/weekly-top-songs/8MT-LQlP35c  
Artist link:   https://jiosaavn.com/artist/arijit-singh/LlRf7ZsVCJo  
Text search:   "Raatan Lambiyan"
```

---

## Installation

Place the two plugin files inside a directory named `saavn`.

---

## Links

* API Used: [saavn.dev](https://saavn.dev/) (self-hosting recommended)
* Kazagumo: [npm](https://www.npmjs.com/package/kazagumo)

---

## Features

* Works without requiring a JioSaavn plugin on your Lavalink server
* Supports direct links for songs, albums, playlists, and artists
* Supports text search via the JioSaavn search engine

---

## How to Use

```js
import { Kazagumo } from 'kazagumo';
import JioSaavn from './plugins/Saavn/index.js';
import { Connectors } from 'shoukaku';

const kazagumo = new Kazagumo(
  {
    plugins: [
      new JioSaavn({
        baseUrl: 'https://saavn.dev/api', // optional (default API endpoint)
        searchLimit: 10, // optional (default: 10, max: 50)
        debug: false, // optional (enable debug logging)
      }),
    ],
  },
  new Connectors.DiscordJS(client),
  Nodes,
);

// Use JioSaavn links directly
kazagumo.search('https://jiosaavn.com/song/excuses/BFUIPyJ0BGY');

// Use JioSaavn as a search engine
kazagumo.search('Raatan Lambiyan', { engine: 'jiosaavn' });
```

---

