# Retirement-calculator
A retirement calculator that helps the user understand how much they should be saving a month.

## Run
Open `index.html` in any browser, or run `npx serve .` from the repo root.

Live demo: enable GitHub Pages on this repo to deploy.

## Methodology

The four scenario cards at the top use a deterministic compound-growth model: an inflation-adjusted annuity for the nest egg target, and the future-value-of-annuity formula for the monthly savings needed.

The Monte Carlo section below addresses what the deterministic model misses: **sequence-of-returns risk**. Two retirees with the same average return over 30 years can end up in very different places — the one who hits a crash in their first few years of withdrawals depletes principal at low prices and never fully recovers, even if later returns are strong. To capture this, the simulator runs 1,000 retirement paths, drawing each year's return independently from a normal distribution with the mean and volatility you set. A Box-Muller transform handles the sampling so there are no extra dependencies. The chart shows the 10th, 50th, and 90th percentile portfolio paths, and the success rate reports the share of runs in which the portfolio survives the full retirement horizon. Past performance does not guarantee future results — this is for educational use only.
