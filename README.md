# Festival Days — Olga + Reza

Ranked festival days for the two of us, scored against both Spotify taste
profiles. Published from the `music_festival_app` project.

Live: https://olga-pyatokha.github.io/festival-days/

This is the slim build: ranked days and per-day artist matches only. The full
build with complete artist weight tables is kept private.

Regenerate with:

```bash
python src/per_day_recommender.py --suffix _vN_slim --slim
```
