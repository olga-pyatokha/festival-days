# Festival Match

Pick any two tracked profiles and get every upcoming festival day ranked by how
well it suits both people, scored against real Spotify listening.

- **App:** https://olga-pyatokha.github.io/festival-days/
- **Static two-person report:** https://olga-pyatokha.github.io/festival-days/report.html

## Scoring

    per-person = 1 - exp(-W / 5)     W = summed weight of matched artists on that bill
    pair       = min(person_a, person_b)

The pair score is a **minimum**, not an average, so one person's zero caps the
day regardless of how much the other likes the bill.

Artist weights combine Spotify top-artist rank (decayed, weighted by term) with
how often an artist appears across saved tracks and playlists.

## Regenerate

```bash
python src/build_app.py                                  # app.html
python src/per_day_recommender.py --suffix _vN_slim --slim   # static report
```

Only weights for artists actually on an upcoming bill are embedded, which keeps
the page under 30 KB and servable as a static file.
