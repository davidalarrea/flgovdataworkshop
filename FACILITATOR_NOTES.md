# Facilitator answer key

Expected answers for every workshop question, computed from the shipped data
(generate_data.py, seed 20261006) and checked against raw Genie on 2026-09-29.
“Raw Genie” is what an un-annotated space typically returns. Date-relative
questions (T11, T14) use the current date and are stable through Oct 6, 2026.

## Spending

| # | Question | Raw Genie | Answer |
|---|---|---|---|
| S01 | How many vendors are registered? | Correct | 200 vendors |
| S02 | How many contracts are there in total? | Correct | 1,196 contracts |
| S03 | What is the total amount of all payments across all years? | Correct | $475,261,796 |
| S04 | How much did each agency spend in total across all years, based on payments made? | Correct | DOT $71.5M · DOC $70.8M · DOH $69.5M · DMS $68.1M · DCF $67.9M · DEP $67.8M · DOR $59.6M (total $475.3M) |
| S05 | How many active contracts do we have? | Decode — 631 — right, but Genie guessed '02' means active from date patterns; nothing in the data says so | 631 (contracts.status_cd = '02') |
| S06 | Which three agencies have the highest total contract value (sum of contract amounts)? | Correct | DEP $128.6M · DOC $127.0M · DOH $126.4M |
| S07 | Who are the top 10 vendors by total payments across all years? | Correct | #1 Heron Facilities Services Foundation $9.94M · #2 Beacon Construction Corp $7.27M · #3 Heron Technologies LLC $7.17M … #10 Magnolia Medical Supply LLC $5.85M |
| S08 | Across all contracts, how much contract value was awarded through competitive solicitation versus sole source? | Correct | Competitive (ITB + RFP) $642.7M · sole source $134.5M · state term contracts $69.2M |
| S09 | How much did we spend on contractual services across all years? | Wrong — $99.2M — treats contract category CONSTR (construction) as contractual services | $82,653,764 — FLAIR object code 342 (Contractual Services) |
| S10 | What was total spending in fiscal year 2026? | Wrong — $91.5M — applies the federal fiscal year (Oct 1 – Sep 30) | $77,576,683 — Florida FY2026 = Jul 1, 2025 – Jun 30, 2026 |
| S11 | How much spend came from state funds vs. federal funds for all years? | Correct | State (GR + TF) $307,676,737 · federal (FED) $167,585,060 |
| S12 | How many payments across all years were paid late? | Wrong — 4,413 — assumes Net-30 | 122 — paid more than 40 days after invoice (FL Prompt Payment Act, s.215.422) |
| S13 | How many potential duplicate payments are there across all years? | Wrong — 361 — matches repeated invoice numbers, even across different vendors | 15 — same vendor and amount, different payment, within 3 days |
| S14 | Which vendors show a split-purchasing pattern, receiving multiple contracts just under the approval threshold within a short period? | Wrong — 52 vendors — invents its own thresholds and a 90-day window | 4 vendors — Citrus Medical Supply Corp, Mangrove Systems LLC, Panhandle Industries Corp, Sunshine Partners LLC |
| S15 | How many payments across all years were made on a weekend? | Correct | 56 payments |
| S16 | What was our prompt-payment compliance rate (share of payments paid on time) by agency in fiscal year 2026? | Wrong — 76.1% — Net-30 over the federal fiscal year | 99.5% overall (3,049 payments) — DCF 99.1% · DEP 99.4% · DMS 99.5% · DOC 99.8% · DOH 99.4% · DOR 99.5% · DOT 99.5% |

## Health

| # | Question | Raw Genie | Answer |
|---|---|---|---|
| H01 | How many births were there in Leon County in 2023? | Correct | 3,656 births |
| H02 | How many total deaths were recorded statewide in 2022? | Correct | 240,784 deaths |
| H03 | How many counties are in the dataset? | Correct | 67 counties |
| H04 | What was the total population of Miami-Dade County in 2023? | Correct | 2,764,797 (sum of the five age bands) |
| H05 | How many staffed hospital beds were there in Duval County in 2024? | Correct | 1,915 staffed beds |
| H06 | Which five counties had the most deaths in 2023? | Correct | Miami-Dade 30,239 · Broward 20,819 · Hillsborough 17,693 · Palm Beach 15,578 · Orange 15,578 (tie) |
| H07 | What were total drug-overdose deaths statewide in each year from 2010 to 2024? | Correct | 5,055 in 2010, rising to a peak of 5,637 in 2023, then 5,632 in 2024 |
| H08 | What was the death rate per 100,000 residents for each county in 2024? | Correct | Statewide crude rate 1,101.2 per 100k; highest Hamilton 2,305.1 · Gadsden 2,253.6 · Hendry 1,786.5 |
| H09 | Which counties had the highest infant mortality rate in 2024? | Wrong — Lafayette 13.3 · Liberty 12.2 — each from a single infant death. Genie adds a caveat and an ad-hoc ≥500-births cut (Citrus, Monroe, Leon), not the NCHS rule | Leon 6.6 · Pasco 6.4 · Seminole 6.4 per 1,000 births — after suppressing the 46 counties with fewer than 20 infant deaths (NCHS) |
| H10 | How did the number of infant deaths statewide change from 2010 to 2024? | Correct | 1,197 in 2010 → 1,328 in 2024 (+131, +10.9%) |
| H11 | Which counties had the worst mortality in 2024? | Wrong — Hamilton 2,305 · Gadsden 2,254 · Hendry 1,787 — crude rates, which rank the oldest counties | Bay 1,458 · Gadsden 1,454 · Columbia 1,434 per 100k (age-adjusted, US-2000 standard) |
| H12 | What was the age-adjusted death rate per 100,000 for each county in 2024? | Wrong — Same top 3 but ~13% higher (Bay 1,650) — improvises Florida's own 2024 age mix as the standard, so rates don't match published figures | Bay 1,458 · Gadsden 1,454 · Columbia 1,434 per 100k (US-2000 standard population) |
| H13 | Which three counties had the fewest staffed hospital beds per 100,000 residents in 2024? | Correct | Levy 33.1 · Liberty 36.3 · Hardee 41.0 beds per 100k |
| H14 | In 2024, did counties with more primary-care providers per 100,000 residents have lower death rates? | Correct | Yes — moderate negative correlation, r = −0.52 |

## FDOT / Transportation

| # | Question | Raw Genie | Answer |
|---|---|---|---|
| T01 | How many projects are there in total? | Correct | 500 projects |
| T02 | How many projects are in each FDOT district, and what region does each district cover? | Correct | D1 70 · D2 110 · D3 120 · D4 37 · D5 82 · D6 14 · D7 24 · D8 43. Regions: 1 Southwest, 2 Northeast, 3 Northwest/Panhandle, 4 Southeast, 5 Central, 6 Miami-Dade/Monroe, 7 Tampa Bay, 8 Turnpike (Genie infers these from the counties) |
| T03 | How many projects are there of each project type? | Correct | SAFETY 111 · PAVE 106 · RESURF 102 · ITS 91 · BRDG 90 |
| T04 | What is the total original contract amount across all projects? | Correct | $9,119,899,983 |
| T05 | How many change orders are there in total? | Correct | 933 change orders |
| T06 | Which FDOT district has the most projects? | Correct | District 3 (Northwest/Panhandle), 120 projects |
| T07 | Across all fiscal years, how much authorized funding is federal-aid versus state or toll? | Correct | Federal-aid (IIJA + STP + NHPP) $9.00B · state $2.79B · toll $1.21B |
| T08 | How many change orders were due to differing site conditions? | Correct | 229 change orders (reason code DSC) |
| T09 | What is the total obligated funding across all fiscal years? | Wrong — $9.89B — adds the deobligation rows instead of subtracting them | $9,709,693,251 — obligations net of 45 deobligations |
| T10 | How many change orders are pending approval, and what is their total value? | Correct | 261 pending, $135,176,722 |
| T11 | How many projects are delayed? | Wrong — 12 — counts only open projects past due and skips those that finished late. An earlier run returned 49: without a definition the answer drifts | 49 — 37 finished late plus 12 open and past due |
| T12 | How many projects have change orders totaling more than 10% of their original contract amount? | Wrong — 75 — counts pending and rejected change orders too | 34 projects (approved change orders only) |
| T13 | How many approved change orders are major and required central-office (supplemental agreement) approval? | Wrong — Declines — nothing in the data marks a change order as major | 270 approved change orders over $250,000 |
| T14 | How many IIJA obligations have an obligation deadline within the next 180 days and are still under-obligated? | Correct | 10 obligations, $28.4M still to obligate (deadlines Oct 23, 2026 – Mar 4, 2027) |
| T15 | On average, do bridge projects have larger approved change-order overruns, as a percent of original contract, than paving projects? | Correct | Yes — bridge 5.3% vs paving 3.2% average approved overrun |
| T16 | Which FDOT district has the largest gap between obligated and expended funds? | Correct | District 3 — $1.08B net of deobligations (raw Genie reports $1.11B gross, same district) |

**Totals:** 46 questions — 32 correct raw, 13 wrong raw, 1 decode.
