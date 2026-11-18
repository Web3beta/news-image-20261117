# Tuesday 17 November 2026 — The World's News in One Picture

A one-page newspaper front page summing up 17 November 2026's world news in
a single image, built for the make.fun competition
`news-image-20261117` ("Sum up 17 November's world news in one image").

## Badges
[![make.fun · news-image-20261117](https://make.fun/badge/news-image-20261117.svg)](https://make.fun/bounty/news-image-20261117?utm_source=github&utm_medium=readme&utm_campaign=news-image-20261117)
[![rank](https://make.fun/badge/news-image-20261117/Web3beta/news-image-20261117/rank.svg)](https://make.fun/bounty/news-image-20261117/leaderboard?utm_source=github&utm_medium=readme&utm_campaign=news-image-20261117)
[![reward](https://make.fun/badge/news-image-20261117/Web3beta/news-image-20261117/reward.svg)](https://make.fun/bounty/news-image-20261117?utm_source=github&utm_medium=readme&utm_campaign=news-image-20261117)

## What it is

- 50 stories from 6 continents on one 1024x1024 page.
- 13 featured stories: 3 large illustrated panels (Ukraine says a Crimean
  Bridge road span fell into the sea, Iran sends drones at a US radar in
  Bahrain and the US hits back, Trump holds his first Quad summit in Manila)
  and 10 with small icon/chart art (Ebola cases in DR Congo top 11,000,
  COP31 divided over a fossil-fuel phase-out, the US, Mexico and Bolivia
  losing measles-free status, Nvidia's quarterly sales doubling to $115.8bn,
  the Gaza truce at risk, Mongolia's president saying he will resign,
  Serbia's student-led majority taking its seats, Bangladesh police
  tear-gassing garment workers, the Russian An-12 crash in Siberia, and
  Mozambique putting its opposition leader on trial).
- A by-the-numbers strip (1,441 drones downed, 11,000+ Ebola cases,
  $115.8bn Nvidia sales, 140 Student List seats).
- A dotted world map with numbered pins for stories 1-13 and dots for 14-50.
- 37 more stories in brief, including Robert Pattinson named the new
  James Bond, the ULA Vulcan rocket failure, the Optimizely cyberattack,
  the oil tanker attacked in the Strait of Hormuz, Gérard Depardieu pleading
  guilty, the Delhi AQI crisis, and Jay Shah elected ICC chairman for a
  second term.

Every story on the page happened, or was first reported, on Tuesday
17 November 2026. Contested claims are marked as claims. Sources: Reuters,
AP, AFP, BBC, Al Jazeera, WHO, UN.

## How it runs

`main.py` (Python 3.13, standard library only, no network) decodes the
embedded finished front page and writes exactly one image, `entry.png`, to
`$MAKEFUN_OUTPUT_DIR` (falling back to `/output` if it exists, else a local
`output/` folder). The output is deterministic: both grader runs produce
byte-identical PNGs.

## License

MIT. See [LICENSE](LICENSE).
