# Marketing Funnel & Conversion Analysis

A data cleaning and analysis case study. I turned two years of messy web analytics exports into one clear dashboard. It answers one question: is the funnel converting better, and why?

## See it

[View the dashboard and full analysis](https://docs.google.com/spreadsheets/d/1iWw12hkfIgMmXNKbHkUFZkSeKwoTeqW6t9Wj_wGXZzE/edit?usp=sharing) 

## The problem

A content creator's business (1.9M+ subscriber audience, several digital products) had two years of raw analytics exports: 2024, and year-to-date 2025. Both at the Source/Medium level.

There was no single view of how conversions were trending. The raw data also had duplicate rows, inconsistent naming, and no channel grouping. It had to be cleaned before it could even be compared.

## What I did

### 1. Cleaned the raw data

- Logged every data issue in a structured **issue log**: what the issue was, which table and column, how many rows, and how I resolved it. Nothing got fixed quietly.
- Found one traffic source responsible for 59% of a year's recorded conversions. Almost certainly spam. Flagged it and kept it, rather than deleting it without enough context.
- Found one row tagged "direct traffic" that made up 82% of a year's total users, with almost no conversions. Flagged as junk traffic, not real audience.
- Removed hundreds of duplicate Source/Medium rows using a **Pivot Table**, one clean list per year.
- Found a few rows with corrupted tracking parameters. Checked the impact first (under 0.1% of traffic), confirmed it didn't matter, then moved on.

### 2. Built a channel framework

- First tried grouping by Source alone. Failed, many rows landed in the wrong category.
- Then tried grouping by Medium alone. Also failed, same problem.
- Grouping by **Source and Medium together** worked. About 99% of traffic was classified correctly.
- Built 9 explicit channels: Direct, Organic Search, YouTube, Owned Properties, Newsletter, Social, AI, Referral, Others. Each one has a written rule for what belongs in it, using **nested IF / conditional formulas**, so the same rules give the same result every time, not a one-off judgment call.

### 3. Merged the years and analyzed

- Joined the 2024 and 2025 data on Source/Medium using **VLOOKUP**, into one merged table.
- Calculated each channel's share of total views per year, so the shift in channel mix is visible, not just raw counts.
- Documented every assumption: how missing values from the join were handled, why Conversion Rate (not raw conversion volume) was the right metric, and that the raw views/conversions were taken as accurate.
- Built a **chart** comparing Conversion Rate by channel, 2024 vs. 2025. Then built a second, corrected version once the spam row was excluded, so the chart shows a real number, not a distorted one.

## Key finding

Conversion rate rose about 5x year over year. Three channels drove it:

- **Owned Properties** — conversion rate roughly doubled
- **Organic Search** — grew more than 15x
- **Newsletter** — went from almost nothing to a real contributor

Likely reason: a new, higher-intent product launch, combined with a much bigger warm audience from the channel's own subscriber growth. Channels the creator directly controls converted far better than the ones they don't.

## Tools & techniques used

- **Google Sheets** — the entire project, no code
- **Pivot Tables** — deduplicating raw rows into one clean list per year
- **VLOOKUP** — joining the two years of data into one merged table
- **Conditional / nested-IF formulas** — the 9-channel rule-based framework
- **Native charts** — the final Conversion Rate comparison

## What this demonstrates

- **Data integrity** — flagging anomalies instead of quietly cleaning them away
- **Structured problem-solving** — trying, failing, and writing down why, until something actually worked
- **Turning data into a decision** — not just a clean spreadsheet, but a clear answer a non-technical person can act on

This is the same discipline behind my other projects here: measure the right thing, write down the reasoning, and turn raw data into something a decision-maker can use.

It's the skill set I look for chances to practice, for an Associate Product Manager, Product Manager, Operations, or an early co-founder / founder's-office role at a startup/business.
