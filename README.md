# Homebase app list

The tiles on Homebase, the locked-down home screen on our Retroid Pocket Classic. Homebase downloads `apps.json` from here every time its home screen opens, and keeps the last copy for when there's no internet.

To add, remove or change a tile, edit `apps.json` and commit. The next time the tiles open, they update.

Making something new for the device? Read the guide in the Homebase repo first: `docs/making-games-for-the-retroid.md` (screen size, buttons, read-aloud, offline, testing, checklist).

Each app:

| Field | Meaning |
| --- | --- |
| `id`, `name`, `url` | Required. The app may open any page under the folder of `url`; nothing else opens. |
| `kind` | `game` (default) or `tool`: which row it's on. |
| `icon`, `color` | Tile picture and color. |
| `grownUp` | `true` keeps it off the tiles; it's in the grown-up menu (Select + Start for 4 seconds, then the PIN). |
| `input` | `pad` (default) or `gamepad` (the page reads the controller itself). |
| `keys` | For games that don't know Homebase: which key each button presses, e.g. `{"a": " "}`. |
| `allow` | Extra URL prefixes the app may open. |

Keep this file valid JSON: if it doesn't parse, Homebase keeps using its last good copy.
