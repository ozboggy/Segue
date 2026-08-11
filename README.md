# Segue DJ

Browser-based auto-DJ. Loads local audio files, reads tempo, bar grid and vocal placement, then plays phrase-aligned segments with beat-matched, pitch-preserving crossfades. Everything runs in the browser; no audio is uploaded.

## Hosting on GitHub Pages

1. Create a repository and commit `index.html` (and this README) at the root.
2. Settings → Pages → Build and deployment → Deploy from a branch → `main` / `root`.
3. The site appears at `https://<user>.github.io/<repo>/`.

That URL is what Spotify needs.

## Spotify setup

1. Go to developer.spotify.com/dashboard and create an app.
2. Set the redirect URI to exactly the URL shown in Segue's Spotify tab, e.g. `https://<user>.github.io/<repo>/`. It must match character for character, trailing slash included.
3. Select the Web Playback SDK and Web API.
4. Copy the Client ID into Segue's Spotify tab, press Connect, approve, then Start player.

Spotify Premium is required — the Web Playback SDK refuses to play on free accounts. Spotify supplies one protected stream, so tracks play as timed segments with a fade between them: no beat-matching, no overlap, no export. The local-file mixer keeps all of that.

## Local files

Chrome and Edge can remember the folder your music lives in ("Add a folder"), which lets saved sets reopen their own audio. Other browsers need files re-added by hand.

Saved sets live in browser storage: library, running order, per-track tempo and cue points, and every blend setting. Playlist files (JSON) can be exported and reopened.
