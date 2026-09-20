# vod-metadata-api

A small Express API that looks up a Twitch video by ID. It exists so the front end in [vod-metadata](https://github.com/gabreusi/vod-metadata) never sees the Twitch credentials.

## Endpoint

```
GET /api/videos/:id
```

The API forwards the ID to Twitch's Helix `videos` endpoint and returns Twitch's JSON response unchanged. If Twitch answers with an error, the API returns the same status. If the credentials are missing, it answers 500. CORS is open. Error messages are in Portuguese.

## Running

Create a `.env` file with the credentials of a Twitch application:

```
TWITCH_CLIENT_ID=
TWITCH_ACCESS_TOKEN=
PORT=3000
```

`PORT` is optional and defaults to 3000.

```bash
npm install
npm run dev
```

For production, `npm run build` compiles to `dist/` and `npm start` runs it.
