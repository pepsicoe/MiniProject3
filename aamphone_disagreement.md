# Disagreement Examples — aamphone & tgarrio1

**Parties:** Aidan Amphonephong (`aamphone`) and Tyler Garriott (`tgarrio1`)

Across both validation logs (100 records), 93 agreed before discussion. Aidan's review of Tyler's projects
produced five disagreements and Tyler's review of Aidan's projects produced two. All seven were resolved:

| # | Project | Field | Author | Validator | Adjudicated | Resolution |
|-|-|-|-|-|-|-|
| 1 | peal_vole | HasRecovered | N/A (artifact gap) | Yes | Yes | ValidatorKept |
| 2 | winvector_vtreat | HasRecovered | No (only sporadic upkeep) | Yes | Yes | ValidatorKept |
| 3 | isl-org_midas | ActivityPattern | irregular | stopped | stopped | ValidatorKept |
| 4 | covid-projections_covid-data-model | ActivityPattern | declining | stopped | stopped | ValidatorKept |
| 5 | hive-researchgroup_volumetric-data-interaction | ActivityPattern | irregular | stopped | stopped | ValidatorKept |
| 6 | movsim_movsim | RecentThemes | Dependency updates:Feature development | Dependency updates:Automated bot contributions | Dependency updates:Automated bot contributions | ValidatorKept |
| 7 | oscaribv_pyaneti | RecentThemes | Bug fixes:Feature development | Bug fixes:Documentation updates | Bug fixes:Documentation updates | ValidatorKept |

The disagreements came from three gaps in the coding guide: what counts as recovery, when to use
**stopped**, and how to classify commits that fit two themes. Each resolution below records the rule we
agreed on so it applies the same way to every project.

## Example 1 — [peal/vole](https://github.com/peal/vole) (HasRecovered)

**Author:** N/A (artifact gap) (`aamphone`)  
**Validator:** Yes (`tgarrio1`)  
**Disagreement:** We both agreed that the computed 67-month gap is a timestamp artifact: commit 9c858f2264 has
a 2014 author date but a 2021 committer date. Aidan stopped at N/A, while Tyler re-evaluated recovery on the
longest genuine gap (December 2023–July 2024).  
**Evidence:** Work resumed on 2024-08-27 with 12 commits that month (BacktrackKit/GraphBacktracking bundling and
dependency updates), release v0.6.0 followed in January 2025, and there were 19 commits in September 2025.  
**Resolution:** **Yes (ValidatorKept).** Our agreed WhyRecovered value already describes the return after the
corrected gap, so Yes keeps the two fields consistent and stays within the binary yes/no codebook.

## Example 2 — [WinVector/vtreat](https://github.com/WinVector/vtreat) (HasRecovered)

**Author:** No (only sporadic upkeep) (`aamphone`)  
**Validator:** Yes (`tgarrio1`)  
**Disagreement:** Does sparse CRAN maintenance after a long gap count as recovery?  
**Evidence:** After the 18-month gap (February 2022–July 2023), 10 new commits followed: a rebuild/recheck in
August 2023, package thinning in June 2024 and documentation examples in January 2025.  
**Resolution:** **Yes (ValidatorKept).** The coding guide defines recovery as becoming active again with new
commits and sets no minimum volume. The low volume Aidan pointed to is already captured by ActivityPattern =
declining and Currentstatus = Inactive. A project can recover from its longest gap and later lapse again.

## Example 3 — [isl-org/MiDaS](https://github.com/isl-org/MiDaS) (ActivityPattern)

**Author:** irregular (`tgarrio1`)  
**Validator:** stopped (`aamphone`)  
**Disagreement:** Should the label follow the WoC series or the official repository?  
**Evidence:** WoC has 200 commits but the official repository has only 88. The extra activity is fork work and
pull-request merge refs. Official commits taper from 35 in 2020 to 2 in 2024, the last is on 2024-08-23,
and the owner archived the repository on 2025-08-25, before the cutoff.  
**Resolution:** **stopped (ValidatorKept).** We judge the official repository. The archive is an explicit end
signal, so the coding guide's stopped fits better than irregular.

## Example 4 — [covid-projections/covid-data-model](https://github.com/covid-projections/covid-data-model) (ActivityPattern)

**Author:** declining (`tgarrio1`)  
**Validator:** stopped (`aamphone`)  
**Disagreement:** For a project that declines and then shuts down, should the label describe the path or the
outcome?  
**Evidence:** Tyler pointed out that Aidan's original evidence leaned on a February 2026 README, which postdates
the cutoff. We re-checked using only pre-cutoff commits. The dataset automation last ran on 2024-07-21. On
2025-01-09, the "Close Registration" commit added "The Covid Act Now website is no longer being updated due to
a lack of reliable data", and on 2025-01-13 the API-usage workflow's schedule was removed. No commits follow
through 2025-09-30.  
**Resolution:** **stopped (ValidatorKept).** The project announced its own end before the cutoff, which matches
stopped.

## Example 5 — [HIVE-ResearchGroup/volumetric-data-interaction](https://github.com/HIVE-ResearchGroup/volumetric-data-interaction) (ActivityPattern)

**Author:** irregular (`tgarrio1`)  
**Validator:** stopped (`aamphone`)  
**Disagreement:** This was the hardest case. There is no archive notice or shutdown commit. Tyler argued that
Aidan's "two years of silence" used an October 2026 date, and that a thesis origin alone does not prove the
project stopped for good.  
**Evidence:** Measured at the cutoff, the project had 11 straight zero-commit months (November 2024–September
2025) after its final pull-request merge on 2024-10-01. Its longest earlier gap was only 2 months. PR #9 is the
last pull request, and the other branches were last updated in 2022.  
**Resolution:** **stopped (ValidatorKept).** We agreed on a rule for all projects: use stopped only when the
project is Inactive at the cutoff and **either** has an explicit end signal **or** has been silent longer than
its own longest earlier gap. The rule also explains the projects we did not call stopped: pyaneti (6 months
silent vs an 8-month earlier gap, and it did resume in October 2025) and vtreat (8 vs 18 months) stay declining.

## Example 6 — [movsim/movsim](https://github.com/movsim/movsim) (RecentThemes)

**Author:** Dependency updates:Feature development (`tgarrio1`)  
**Validator:** Dependency updates:Automated bot contributions (`aamphone`)  
**Disagreement:** Do Dependabot bumps count as Dependency updates, Automated bot contributions, or both? Tyler
also asked us to confirm that we were counting the same ten commits.  
**Evidence:** Using Tyler's WoC window (April 2024–September 2025): 3 human dependency/build changes, 3
Dependabot commits, 1 feature commit, 1 README commit and 2 parameter tweaks.  
**Resolution:** **Dependency updates:Automated bot contributions (ValidatorKept).** Rule: bot-authored commits
count as Automated bot contributions, and human-authored version bumps or merges count as Dependency updates.
Under that rule, Feature development has only one commit and cannot be second.

## Example 7 — [oscaribv/pyaneti](https://github.com/oscaribv/pyaneti) (RecentThemes)

**Author:** Bug fixes:Feature development (`tgarrio1`)  
**Validator:** Bug fixes:Documentation updates (`aamphone`)  
**Disagreement:** Do commits that add example inputs count as feature development or documentation?  
**Evidence:** In the last 10 commits before the cutoff there are 5 fixes, 4 example commits and 1 makefile
tweak. The 4 example commits touch only input files and data under `inpy/`, with no source changes.  
**Resolution:** **Bug fixes:Documentation updates (ValidatorKept).** Commits that only add or edit usage
examples count as documentation.
