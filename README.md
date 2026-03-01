# Gear Clock

An animated SVG gear train that demonstrates mechanical clock reduction ratios. A small input gear spinning at 1 revolution per second drives a compound gear train, progressively reducing speed through meshing triangular-tooth gears — all the way down to 1 revolution per 12 hours.

## Gear Train

**17 gears, 43,200:1 total reduction**

| Stage | Gears | Ratio | Cumulative | Result |
|-------|-------|-------|------------|--------|
| Input | **A** (10 teeth) | — | 1:1 | 1 rev/sec |
| 1 | A → **B** (60t) | 6:1 | 6:1 | |
| 2 | **C** (10t, on B) → **D** (60t) | 6:1 | 36:1 | |
| 3 | **E** (12t, on D) → **F** (20t) | 5/3:1 | 60:1 | **Seconds hand** (1 rev/min) |
| 4 | **G** (10t, on F) → **H** (60t) | 6:1 | 360:1 | |
| 5 | **I** (10t, on H) → **M** (10t, idler) → **J** (20t) | 2:1 | 720:1 | Direction reversal via idler |
| 6 | **K** (10t, on J) → **L** (50t) | 5:1 | 3,600:1 | **Minute hand** (1 rev/hr) |
| 7 | **N** (10t, on L) → **O** (30t) | 3:1 | 10,800:1 | |
| 8 | **P** (10t, on O) → **Q** (40t) | 4:1 | 43,200:1 | **Hour hand** (1 rev/12 hr) |

## How It Works

**Compound gears** are the key — two gears of different sizes fixed to the same shaft. The large gear is driven slowly, and a small gear on that same shaft drives the next large gear, multiplying the reduction ratios at each stage.

An **idler gear** (M) is used between stages 4 and 5 to reverse direction without changing the ratio, ensuring the minute hand rotates clockwise.

All gears use triangular tooth profiles with matching module (tooth size = 2.5), ensuring teeth mesh properly. Phase alignment is calculated so teeth interlock correctly at each mesh point.

The clock hands are physically driven by their respective gears — the needle is part of the gear's SVG group, so it rotates exactly as fast as the gear turns. On load, the animation is offset using `Date()` so the hands show the current time.

## Running

Open `index.html` in a browser. No dependencies.

```sh
npm run dev    # opens index.html
npm run deploy # publish to GitHub Pages
```

## Tech

- Single HTML file with inline SVG and JavaScript
- Gear paths generated procedurally
- Animation via `requestAnimationFrame`
- Responsive viewport scaling for mobile
- Portrait layout for future mobile/app deployment
