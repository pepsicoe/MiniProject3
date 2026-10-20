# Validation Reflection — aamphone

Tyler (`tgarrio1`) and I each validated the other's ten projects, which produced 100 records across five
fields. We agreed on 93 before discussion and all 100 after it. Currentstatus and WhyRecovered matched
everywhere: the first has a mechanical six-month rule, and for the second we both read the same causes from
the commit messages. The disagreements fell in ActivityPattern (85% agreement, κ = 0.78), HasRecovered (90%,
κ = 0.75) and RecentThemes (90%). None of them were misreadings of the data. Each one came from a place where
the coding guide leaves a judgment call open, and resolving them gave us a set of rules that now apply to all
20 projects.

**Signals before long gaps.** Across both sets of projects, the clearest warning sign was a release or other
milestone followed by nothing. pressio paused right after tagging v0.10.0, causact went quiet for ten months
after its JOSS paper and v0.4.3, dicomweb-client stopped after the v0.59.x releases, and aglm went 32 months
without a commit after its CRAN 0.4.0 release and a final round of fixes in January 2022. A second signal was maintenance-only work: vtreat's last pre-gap
commits only edited example articles, hh-suite's were CI, SIMDe and compiler fixes, and movsim's last commit
before its 17-month gap updated libraries for Java 11. The third was dependence on one person. biomaj-download
stopped when the developer who wrote 8 of its last 10 commits stopped, and pyaneti's gaps track a single
maintainer's availability. Early-stage projects such as CUDA.jl and ANTsPy showed a different version of the
same thing: an initial burst of setup work, then a pause before outside contributors arrived.

**What triggers recovery.** Recoveries were rarely spontaneous. Most were forced by something outside the
project: a compiler or dependency change (hh-suite and GCC 13, ANTsPy and GCC 8.1, biomaj-download's
requirement and protobuf fixes, movsim's Dependabot bumps) or a package-registry check (aglm's and vtreat's
CRAN maintenance). Others came from a change in direction (ArviZ becoming independent of PyMC3, causact
replacing greta with NumPyro), from users (dicomweb-client's PR #108 came from a team using the library in
their own project), or from people: hepml-livingreview's maintainer coming back from time away, and HIVE's
handoff to a new developer. This is why we settled vtreat as recovered. The coding guide lists new commits as
evidence of recovery and sets no minimum volume, and the low volume is already recorded by its "declining" pattern and "Inactive" status. Keeping
these fields separate lets a project recover and later lapse again, which several of ours did.

**When gaps don't mean project death.** A long gap only meant something once we compared it with the project's
own history. Two of my "gaps" were not inactivity at all. vole's 67 months came from a website commit that kept
its 2014 author date, and python-meegkit's 95 months were imported history from an earlier implementation.
pyaneti was Inactive at the cutoff after six quiet months, but it had already gone eight months without commits
twice before, and it did resume in October 2025. The projects that really ended looked different. MiDaS was archived,
covid-data-model announced in January 2025 that it was "no longer being updated," and HIVE's prototype went 11
months without a commit after never before pausing for more than two. That pattern became our rule for
**stopped**: the project must be Inactive at the cutoff and either have an explicit end signal or be silent
for longer than its own longest earlier gap.

**Recurring interpretation pitfalls.** Three pitfalls came up repeatedly. The first was treating World of Code
counts as the project's own history. WoC includes fork commits and pull-request merge refs: MiDaS shows 200
commits in WoC but has 88 upstream, and many of hh-suite's "recovery" rows are pull-request merges. We
resolved this by checking disputed labels against the official repository rather than trusting the series. The second
was using evidence from after the cutoff. My first argument for HIVE relied on two years of silence counted to
October 2026, and my covid-data-model evidence leaned on a 2026 README. Tyler pointed this out, and we
re-anchored both cases to 2025-09-30, where pre-cutoff evidence still supported "stopped." The third was
overlapping categories. "Stopped" is in the coding guide but was missing from the MiniProject2 list, so both of
us originally described trajectories instead. Dependabot bumps fit both "Dependency updates" and "Automated bot
contributions," and pyaneti's example files could be read as features or documentation. We settled the theme
cases by classifying on the commit's author (bot vs human) and on the file paths it touches (example inputs
only = documentation).

**Suggested coding-guide changes.** Our resolutions point to four additions: (1) define recovery as any new
commits after the gap, with volume recorded elsewhere; (2) add the stopped rule above and list "stopped" in
every place the categories appear; (3) give tie-break rules for overlapping themes based on author and changed
files; and (4) require checking WoC series against the upstream default branch before interpreting a gap.
The biggest lesson from validation was that most of our disagreements were about method rather than about
facts. Writing down how we decided, not just what we decided, is what brought agreement to 100%.
