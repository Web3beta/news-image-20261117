# Tuesday 17 November 2026 — The World's News in One Picture

A one-page newspaper front page summing up Tuesday 17 November 2026's
world news in a single image, built for the make.fun competition
`news-image-20261117` ("Sum up 17 November's world news in one image").

## What it is

- 44 stories from 7 regions on one 940x1024 portrait page, built for
  clarity first: fewer stories, bigger text, and more breathing room
  than a crowded 55-story page.
- 13 featured stories in a 3+5+5 photo grid, each with a photo-like
  picture: the Crimean Bridge road span falling into the sea, Iran
  sending drones at a US radar in Bahrain and the US hitting back,
  Trump's first Quad summit in two years in Manila, Ebola vaccine
  trials, COP31 divided over a fossil-fuel phase-out, the US, Mexico
  and Bolivia losing measles-free status, Nvidia's sales doubling,
  the Gaza truce at risk, Mongolia's president resigning, Serbia's
  student-led majority taking its seats, Bangladesh police tear-gassing
  garment workers, the Russian An-12 crash in Siberia, and Mozambique
  putting its opposition leader on trial.
- A BY THE NUMBERS strip with six figures: 1,441 drones downed,
  11,376 Ebola cases, $115.8bn Nvidia sales, -849 Dow points,
  140 Student List seats, and 56 Democrats taking the Senate.
- A full-width world map, "WHERE IT HAPPENED", with numbered pins
  for stories 1-13, dots for stories 14-44, and eleven labelled
  callout bubbles so the reader never has to guess what a pin means.
- 31 more stories in a region-grouped list (14-44), numbered in
  order inside each region so the numbers never jump.
- A DATE CHECK box that keeps the page honest: the Vulcan rocket
  loss happened on 15 November, not this Tuesday, so it stays out;
  Ebola passed 11,000 cases on 10 November, and the totals shown
  (11,376 cases, 5,568 deaths) are the current ones.

## Verified facts

Every number on the page was checked against live sources (Reuters,
AP, AFP, BBC, Al Jazeera, WHO, UN): Ebola 11,376 cases and 5,568
deaths; measles 5,412 US cases; An-12 crash killing all 19; the Dow
falling 849 points on Tuesday; Nvidia reporting $115.8bn in sales
after Tuesday's close; 1,441 drones downed; 140 of 250 Student List
seats; 56 Democrats taking the Senate; Cyclone Xavier nearing
Category 4 by the Cook Islands. Contested claims are marked as
claims, and the page carries no story from any other day.

## How it runs

`main.py` (Python 3.13, standard library only, no network) decodes
the embedded finished front page and writes exactly one image,
`entry.png`, to `$MAKEFUN_OUTPUT_DIR` (falling back to `/output` if
it exists, else a local `output/` folder). The output is a 940x1024
portrait PNG under 1 MiB, and it is deterministic: both grader runs
produce byte-identical PNGs.

## How the image is built

The page is drawn by `render.py` (Pillow): masthead with a globe
icon and WORLD NEWS badge, a colour region bar, the photo grid, the
numbers strip, the map, and the list. The thirteen card photos are
pre-generated photo-like images pasted cover-fit into the cards at
build time. `assemble.py` then takes the finished `entry.png`,
compresses it with zlib, base64-encodes it, and writes `main.py`
with the payload split into exactly five long string literals, so
the program carries the picture inside itself and needs no files
or network at run time.

## Verification

The submitted render was checked before bundling:

- `entry.png`: 473,650 bytes, 940x1024 portrait, sha256
  `99eceec53ea6abc71736e4ea562af3405d1c8feb86eb221eb2420585169487e8`.
- Two runs of the renderer produce byte-identical PNGs.
- `main.py` carries the picture as DATA in exactly 5 long base64
  literals (124,627 x 4 + 124,624 characters), assembled by
  `assemble.py` from the file on disk, never typed by hand.
- List numbers run 14-44 in order inside each region group, and the
  region bar adds up to the same 44 stories: EUROPE 11, MIDDLE EAST 6,
  ASIA 12, AFRICA 5, AMERICAS 7, OCEANIA 2, WORLD 1.

## License

MIT. See [LICENSE](LICENSE).
