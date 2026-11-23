# Ten Classics

Thirty structured indoor cycling sessions for the [Indoor Bike](https://indoorbike.app/) app, in three levels of ten.

- `beginner.json` - first sessions: 20 to 45 minutes, nothing longer than eight minutes at a time.
- `advanced.json` - the classics: tempo, sweet spot, threshold, over-unders, short VO2max.
- `expert.json` - long blocks and hard intervals, plus a recovery ride and an FTP test.

Every session runs in ERG mode and is an hour or less.

## Install in the app

Open the community browser, or add the manifest URL by hand:

```
https://herbkk.github.io/ten-classics/manifest.json
```

## Publish

Host the four JSON files over HTTPS with CORS enabled. GitHub Pages does both by default.

Then open a pull request against [the app repository](https://codefloe.com/SnappTechnology/IndoorCyclingApp) adding one entry to `website/registry.json`:

```json
{
  "id": "ten-classics",
  "name": "Ten Classics",
  "description": "Thirty structured sessions in three levels. Ten beginner rides, ten advanced, ten expert, none longer than an hour.",
  "author": "Herbert",
  "manifestUrl": "https://herbkk.github.io/ten-classics/manifest.json",
  "tags": ["Beginner", "Advanced", "Expert", "Threshold", "VO2 Max", "Sweet Spot", "Test"],
  "homepage": "https://github.com/herbkk/ten-classics"
}
```

## Editing

- Bump `version` on the bundle you changed, or the app keeps serving its cached copy.
- Bump `updatedEpoch` in `manifest.json` when you publish; it is milliseconds, 13 digits.
- Workout ids start with `ten-classics-` so they cannot collide with another repository.
- `schemaVersion: 2` on a workout is only needed when a segment carries a cadence target.
- GitHub Pages serves `Cache-Control: max-age=600`, so a change can take up to ten minutes to appear.

## License

The workouts are my own description of standard training sessions. Do with them as you like.
