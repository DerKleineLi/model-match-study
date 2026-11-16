# Model Match user study

A pairwise user study comparing 3D scene reconstructions of base models. Each screen showed one real photo of a room
and two renders of reconstructions by different methods from the same camera. Raters answered four questions per
screen, 30 screens per round.

The study ran from 2026-11-11 to 2026-11-16 at `derkleineli.github.io/userstudy/` and is now closed. This repository
keeps the study page (`index.html`, `img/`) and its results.

## Results

[`results/votes.csv`](results/votes.csv): 716 answered screens from 32 raters, last vote 2026-11-14 18:47 UTC.
One row per screen, exported from the collecting Google Sheet. One id appears twice (a resend), so there are 715 unique
votes. Deduplicate by `id`.

Raters' self-entered names and browser user agents are not included.

| Column | Meaning |
| --- | --- |
| `received` | Time the collector stored the row (UTC) |
| `id` | Vote id, `<rater>_<ms timestamp>` |
| `t` | Time the rater submitted the screen (UTC, browser clock) |
| `rater` | Random id kept in the rater's browser |
| `session` | One round of 30 screens |
| `scene`, `view` | Scene id and camera view index |
| `a`, `b` | The two methods compared |
| `left` | Which method was shown as Render A (on the left): `a` or `b` |
| `objects`, `layout`, `image`, `overall` | Answer per question: `a` = method `a` better, `b` = method `b` better, `s` = about equal |
| `ms` | Time spent on the screen, in milliseconds |
| `qv` | Question set version |
| `kind` | `human` for every row |

The four questions:

- **Objects:** which reconstructs the objects in the photo more completely and more faithfully, with fewer missing,
  extra or wrong-looking ones?
- **Layout:** which places the objects and room surfaces more like the photo?
- **Appearance** (`image`): which image as a whole looks more like the photo?
- **Overall:** if you could keep only one reconstruction of this view, which would you keep?
