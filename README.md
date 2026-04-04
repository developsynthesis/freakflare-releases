# FreakFlare Releases

Public release metadata for the FreakFlare app. The FreakFlare app fetches `releases.json` from this repo on launch to check for available updates and display release notes to users.

## How It Works

1. App launches and fetches `releases.json` via raw GitHub URL
2. Compares the user's current app/firmware version against `latestVersion`
3. If a newer version is available, shows a dialog with release notes for all versions between the user's version and the latest
4. User can update or snooze the notification for 48 hours

## Files

- `releases.json` — App and firmware version metadata with release notes
- `README.md` — This file

## Updating

When publishing a new app or firmware release:

1. Add a new entry to the top of the appropriate `releases` array in `releases.json`
2. Update the `latestVersion` field
3. Update store URLs if needed
4. Commit and push to this repo

## Schema

See `releases.json` for the current schema. Key fields:

- `app.latestVersion` — Latest published app version
- `app.storeUrl.ios` / `app.storeUrl.android` — App store links
- `app.releases[]` — Version-tagged release notes (newest first)
- `firmware.latestVersion` — Latest firmware version bundled with the app
- `firmware.releases[]` — Version-tagged firmware release notes (newest first)

## Privacy

FreakFlare does not collect, transmit, or store any user data. The app does not track usage, location, or device identifiers. The only network request the app makes is fetching this file (`releases.json`) to check for available updates. No information about the user or their device is sent in that request.

This repo contains only version numbers and release notes text. No user data, no credentials, no device identifiers.
