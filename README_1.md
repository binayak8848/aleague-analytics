# Untapped Talent: A-League Analytics

Statistical analysis of Australian A-League Men player data, built for the
[Untapped Talent](https://untappedtalentfootball.blogspot.com) blog (see the
[latest post](https://untappedtalentfootball.blogspot.com/2026/07/do-league-defenders-actually-tackle.html)), covering
Australian football scouting and analysis that doesn't get much coverage
elsewhere.

## Current Analysis

**Do A-League Defenders Actually Tackle More Than Midfielders?**
- Full write-up: [blog post](https://untappedtalentfootball.blogspot.com/2026/07/do-league-defenders-actually-tackle.html)
- Full statistical breakdown: [RPubs report](https://rpubs.com/Binayakhero/aleague-tackles-by-position)
- Code: [`aleague_tackles_analysis.Rmd`](./aleague_tackles_analysis.Rmd)

**Method:** Season-long player data (2025/26 A-League Men) grouped by primary
position (DF/MF/FW). Distribution normality checked via Shapiro-Wilk, group
differences tested via Kruskal-Wallis, and pairwise comparisons via Dunn's
test with Bonferroni correction.

**Finding:** Forwards tackle significantly less than both other positions
(p < 0.001), but Defenders and Midfielders show no statistically significant
difference in Tackles Won (p = 1.00, adjusted), despite the positional
label.

## Data Sources & a Note on Data Availability

Player data was manually exported from [FBref](https://fbref.com) (A-League
Men, 2025/26 season). Data sourced from FBref.com / Sports Reference LLC,
credited here per their [data use terms](https://www.sports-reference.com/termsofuse.html).

FBref lost its Opta data licence in January 2026,
which removed advanced defensive metrics (Clearances, Blocks, progressive
passing stats) site-wide. This analysis uses the basic stats that remained
available (Tackles Won, Interceptions, minutes played, etc.) rather than the
deeper Opta-sourced metrics.

## Repo Structure

```
├── aleague_tackles_analysis.Rmd   # Full reproducible analysis
├── A_League_Stats_Cleaned.xlsx    # Cleaned player standard stats
├── Defense_Passing_Cleaned.xlsx   # Cleaned defensive/passing stats
└── README.md
```

## Requirements

```r
install.packages(c("readxl", "dplyr", "ggplot2", "FSA"))
```

## More Coming

This is an ongoing project. Next up: Interceptions by position, followed by
a broader look at U23 centre-backs to watch in the A-League.
