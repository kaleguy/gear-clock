# Gear Clock

An animated SVG gear train that demonstrates mechanical clock reduction ratios. A small input gear spinning at 1 revolution per second drives a compound gear train, progressively reducing speed through meshing triangular-tooth gears.

## Current State

**8 gears, 360:1 total reduction** (working toward 43,200:1 for a full 12-hour clock)

- **A** (10 teeth) — input, 1 rev/sec
- **B** (60 teeth) — 6:1 reduction
- **C** (10 teeth, compound on B) → **D** (60 teeth) — another 6:1
- **E** (12 teeth, compound on D) → **F** (20 teeth) — 5/3:1, completes 60:1 (1 rev/min with seconds dial)
- **G** (10 teeth, compound on F) → **H** (60 teeth) — 6:1 more, 360:1 total (1 rev/6 min)

### Remaining to build

- **Minute hand**: 10:1 more reduction from H → 1 rev/hour (3,600:1 total)
- **Hour hand**: 12:1 more reduction → 1 rev/12 hours (43,200:1 total)

## How It Works

**Compound gears** are the key — two gears of different sizes fixed to the same shaft. The large gear is driven slowly, and a small gear on that same shaft drives the next large gear, multiplying the reduction ratios at each stage.

All gears use triangular tooth profiles with matching module (tooth size = 2.5), ensuring teeth mesh properly. Phase alignment is calculated so teeth interlock correctly at each mesh point.

## Running

Open `index.html` in a browser. No dependencies.

## Tech

- Single HTML file with inline SVG and JavaScript
- Gear paths generated procedurally
- Animation via `requestAnimationFrame`
- Portrait layout for future mobile/app deployment
