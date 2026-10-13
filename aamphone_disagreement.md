# Disagreement Examples — aamphone & tgarrio1

45 of 50 records agreed. The five disagreements fall into two groups: three
ActivityPattern labels where the coding guide's **stopped** category competes with the trajectory label
used in MiniProject2 (whose README list did not include "stopped"), and two RecentThemes pairs that hinge on
how to classify Dependabot commits and example/tutorial files.

Fill in the **Resolution** and **Time to resolve** lines during the discussion; the times feed
`MeanResolutionTime_min` in Part 3.

## Example 1 — [isl-org/MiDaS](https://github.com/isl-org/MiDaS) (ActivityPattern)

**Author:** irregular (`tgarrio1`)  
**Validator:** stopped (`aamphone`)  
**Reason:** The WoC monthly series looks irregular because fork merges inflate it (200 WoC commits vs 88 on
the official repository). Upstream activity tapers from 35 commits in 2020 to 5 in 2023 and 2 in 2024, the
last official commit is 2024-08-23 (SECURITY.md), and GitHub shows the repository was archived on 2025-08-25.  
**Question to settle:** Should ActivityPattern be judged on the official repository or on the WoC series that
includes fork activity?  
**Resolution:** Pending discussion.  
**Time to resolve:** __ min

## Example 2 — [covid-projections/covid-data-model](https://github.com/covid-projections/covid-data-model) (ActivityPattern)

**Author:** declining (`tgarrio1`)  
**Validator:** stopped (`aamphone`)  
**Reason:** The 2020–2024 path is a clean decline (7,248 → 4,055 → 2,398 → 588 → 138 commits per year), but
the dataset automation ended on 2024-07-21, the API registration was closed in January 2025, and the
February 2026 README marks the project archived and winding down.  
**Question to settle:** When a project declines and is then formally shut down, does the label describe the
trajectory (declining) or the end state (stopped)?  
**Resolution:** Pending discussion.  
**Time to resolve:** __ min

## Example 3 — [HIVE-ResearchGroup/volumetric-data-interaction](https://github.com/HIVE-ResearchGroup/volumetric-data-interaction) (ActivityPattern)

**Author:** irregular (`tgarrio1`)  
**Validator:** stopped (`aamphone`)  
**Reason:** Yearly volume rises (11 → 294 → 588 → 696) with large monthly bursts, then nothing after the
PR #9 merge on 2024-10-01 — two years of silence as of October 2026. The README describes a master's-thesis
prototype, which fits a finished project.  
**Question to settle:** Same as Example 2, plus whether "irregular" (month-to-month bursts) or the long-term
outcome should drive the label.  
**Resolution:** Pending discussion.  
**Time to resolve:** __ min

## Example 4 — [movsim/movsim](https://github.com/movsim/movsim) (RecentThemes)

**Author:** Dependency updates:Feature development (`tgarrio1`)  
**Validator:** Dependency updates:Automated bot contributions (`aamphone`)  
**Reason:** In the last 10 commits before 2025-09-30, five are dependency work, two of them authored by
Dependabot. Feature work is one clear commit (improved FVD model, 2024-05-01) plus at most one scenario
tweak. The WoC window has three Dependabot rows.  
**Question to settle:** Do Dependabot bumps count as "Dependency updates", "Automated bot contributions",
or both?  
**Resolution:** Pending discussion.  
**Time to resolve:** __ min

## Example 5 — [oscaribv/pyaneti](https://github.com/oscaribv/pyaneti) (RecentThemes)

**Author:** Bug fixes:Feature development (`tgarrio1`)  
**Validator:** Bug fixes:Documentation updates (`aamphone`)  
**Reason:** Both agree bug fixes come first. The disputed commits ("Added 1D GP example…", "Added K2-233
example") only add `input_fit.py` and data files under `inpy/`, i.e. usage examples rather than new code
functionality.  
**Question to settle:** Are example/tutorial inputs documentation or feature development?  
**Resolution:** Pending discussion.  
**Time to resolve:** __ min
