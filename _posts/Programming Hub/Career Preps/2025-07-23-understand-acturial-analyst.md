---
layout: post
title: Understand Actuarial Analyst
date: 2025-07-23 15:58 -0700
description: Actuary and Insurance Concepts Recap
author: khoa_pham
categories: [Programming Hub, Career Preps]
pin: false
math: true
mermaid: true
toc: true
comments: true
---

## Understand Insurance Industry and Actuarial Concepts

### How Insurance Companies Make Money?
> Policyholders pay premiums ($100) to insurance companies, then they invest and return of $130, which then use this money to cover claims and expenses ($80 + $40 = $120). The remaining $10 is profit.

**Areas Insurance Companies Must Pay:**
- Claims – Paid when a policyholder is owed payment (e.g., car accident, health issues)
- Expenses – Salaries, equipment, advertising, commissions, etc.

**Areas Insurance Companies Can Make Money:**
- Money from Investments (Bonds, Shares, Mortgages, etc.)
- Sell assets


### Types of Life Insurance
> Link to article: [Types of Life Insurance](https://www.ratehub.ca/insurance/life/types-of-life-insurance)

**Terms and Concepts:**
- How Insurance Works (in General)
- Premiums
- Beneficiaries
- Death Benefits
- Term Life Insurance
- Medical testing
- Permanent Life Insurance
- Renewable Term Insurance
- Convertible Term Insurance
- Joint Life Insurance
- Combined Insurance Policy
- Term-to-100 Life Insurance (T100)
- Whole Life Insurance
- Cash Surrender Value
- Non-Participating vs Participating Insurance Policies
- Policy Dividends
- Universal Life Insurance
- Guaranteed Life Insurance
- No-Medical Life Insurance
- Mortgage Life Insurance


### Long-Term Care Insurance
> Link to article: [Mechanics and Basics of Long-Term Care Rate Increases](https://www.soa.org/globalassets/assets/Library/Newsletters/Long-Term-Care/2014/august/ltc-2014-iss36-gordon.pdf)

**Terms and Concepts:**
- Loss Ratios
- Issue Age Rating vs. Attained Age Rating
- Morbidity Assumptions
- Persistence Assumptions
- Interest Rate Assumptions (impact of 2007/2008 recession)
- Lapse Rate Assumptions
- Shock Lapses
- Reserves
- Filing for Rate Increases
- Low Frequency, High Severity Claims vs. High Frequency, Low Severity Claims
- General Population Data vs Insured Population Data
- Elimination Period

Long-Term Care insurance is a fairly new type of insurance. It is priced differently than most other health insurance products.

For most health insurance products, the insurance company can change the premium year-to-year. So, if any incorrect pricing assumptions are made, the premium can be easily adjusted the next year to reflect the correct pricing assumptions.

However, LTC insurance offers a level premium that stays the same year-to-year. So, if pricing assumptions are incorrect at the beginning, there is not a way to adjust them. They’re locked in.

That being said, the assumptions used to price this new type of insurance were so incorrect, that insurance companies are now requesting (from regulators) that they be allowed to adjust their premiums in order to sustain these products and keep them financially sound. This is called “filing for a rate increase”.

At first glance, the rate increases seem unnecessary due to low loss ratios and higher-than-expected persistency. However, this article digs deeper into why that is not the case.

Additionally, the article discusses the incorrect assumptions.

In particular, experience has shown that the persistency assumptions made when originally pricing these policies was incorrect. Policyholders are keeping their policy longer than anticipated. This is one reason that rates need to increase.

In addition, the interest rate assumptions for these products were set before the 2007/2008 economic recession. Interest rates after the recession were much lower than assumed. This is another reason for the rate increases.

Lastly, morbidity assumptions used when originally pricing LTC insurance was based on general population data. Now we have more accurate data based on the insured population. This new, more accurate data shows that the morbidity rates used for pricing (based on general population data) were too high in early years and too low in later years.


### IBNR Reserve

An IBNR Reserve ensures that the insurance company has enough money to cover incurred claims that have not yet been reported.

> Link to article: [Using member-level predictive models to calculate IBNR reserves](https://www.theactuarymagazine.org/anticipating-events/)

**Terms and Concepts:**
- Predictive Models
- Incurred But Not Reported (IBNR) Reserves
- Completion Factor IBNR Calculation Method
- Projection IBNR Calculation Method
- High Frequency, Low Severity Claims
- Pools, Risks, Groups
- Leading Indicators

Traditionally, insurance companies use an IBNR calculation in agreggate, meaning there isn’t an IBNR reserve attributable to each insured member. Two common methods are the completion factor method and the projection method.

These methods allow for a fairly easy IBNR calculation, but all risks (or members, or insureds) are treated exactly the same. However, as we know, that’s not a realistic assumption. Every member is a bit different and therefore we would expect different claim amounts and frequencies from them in the future.

The article speculates that a predictive model may be able to more accurately estimate the future claims (and thus, an IBNR), and it could do this at a member level (rather than in aggregate). Then, an insurance company could sum up all the individual member-level estimates to determine the total IBNR necessary for the group.

The biggest advantage to using a predictive model would be the potential increase in accuracy. The case study in the article suggests that an increase in accuracy would, in fact, be a benefit.

The predictive model method would also allow insurers to determine an IBNR for any subset of a group more easily and accurately.However, there are many other considerations when deciding whether or not a predictive model for IBNR calculation is feasble. The video and article goes into those thoughts.


### Insurance Deductibles

### Actuarial Tables

### Financial Statements
- Balance Sheets
- Income Statements



## Technical Skills

### Excel & VBA
#### 1) Beginner Level
- Save as a macro-enabled workbook
- Formatting (Coloring cells, Adding borders, Column width)
- Autofill & Flash Fill
- Freeze panes, Hide rows/columns
- Find & Replace
- Sort & Filter
- Linking to other tabs

#### 2) Intermediate Level
- Named ranges, Name manager
- Relative, Absolute, and Mixed References
- Conditional Formatting
- Drop-down boxes, Data Validation
- Simple formulas, Nested formulas (IF statements)
- Basic functions (SUM, AVERAGE, MIN, MAX)

#### 3) Advanced Level
- INDEX, MATCH formulas
- HLOOKUP, VLOOKUP formulas
- Advanced functions (SUMIF, COUNTIF, IFERROR)
- Pivot Tables
- Graphs and Charts

#### 4) Visual Basic for Applications (VBA)
- Loops
- Debugging
- Recording Macros, Button Creation