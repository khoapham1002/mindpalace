---
layout: post
title: Risk and Insurance
date: 2025-08-01 18:15 -0700
description: Introduction to insurance concepts for actuarial study
author: khoa_pham
categories: [Programming Hub, Career Preps]
tags: [actuarial]
pin: false
math: true
toc: true
comments: true
---

## I. INTRODUCTION

People seek security. A sense of security may be the next basic goal after food, clothing, and shelter. An individual with economic security is fairly certain that he can satisfy present and future needs such as food, shelter, and medical care.

Economic risk is the possibility of losing economic security. Most economic risk comes from variation around the expected outcome.

One measure of risk is the **standard deviation** of possible outcomes:

$$
\sigma = \sqrt{\mathbb{E}[(X - \mathbb{E}[X])^2]}
$$

For example, suppose the expected repair cost after an accident is \\$2,500 for both a Porsche and a Toyota:

* Porsche standard deviation = \\$1,000
* Toyota standard deviation = \\$400

If repair costs are normally distributed, the probability that repairs cost more than \\$3,000 is:

* 31% for the Porsche
* 11% for the Toyota

Even with the same expected cost, the Porsche is riskier because the outcomes vary more.

Modern society is full of similar risks:

* a homeowner may face a major loss from fire
* a driver may lose money if a car is damaged
* a driver may also be liable for third-party injury or property damage

Historically, risk was handled informally through community support. Over time, that cooperative pooling idea became formalized into insurance.

## II. HOW INSURANCE WORKS

Insurance is an agreement where, for a stated payment called the **premium**, one party, the **insurer**, agrees to pay the other party, the **policyholder** or beneficiary, a defined amount upon the occurrence of a specified loss.

The insurer estimates:

* expected losses for the pool
* possible variation around those losses

Then it charges premiums that should be sufficient, in total, to cover projected claim payments.

Normally, only a small percentage of policyholders suffer losses. Their claims are paid using premiums collected from the full pool. In this way, the entire pool compensates the unfortunate few.

Important terminology:

* **Policyholder**: the person insured
* **Insurer**: the insurance company
* **Premium**: the amount paid for coverage
* **Policy**: the insurance contract
* **Peril**: a cause of loss, such as fire, theft, hurricane, or heart attack
* **Hazard**: a condition that increases the probability or severity of loss

Examples of hazards:

* smoking for healthcare losses
* poor wiring for fire losses
* living in California for earthquake losses

Insurance lets the policyholder exchange an uncertain loss for a known premium. In that sense, the policyholder transfers economic risk to the insurer.

## III. A MATHEMATICAL EXPLANATION

Losses depend on two random variables:

* **Frequency**: the number of losses in a period
* **Severity**: the amount of loss, given that a loss occurs

By combining frequency and severity, we get the overall loss distribution.

### Example: Car Accident Loss Distribution

Consider a car owner with:

* 80% chance of no accidents in a year
* 20% chance of one accident
* 0% chance of more than one accident

If an accident occurs, the severity is:

* 50% chance repairs cost \\$500
* 40% chance repairs cost \\$5,000
* 10% chance the car must be replaced for \\$15,000

The resulting loss distribution is:

* $P(X=0)=0.80$
* $P(X=500)=0.10$
* $P(X=5000)=0.08$
* $P(X=15000)=0.02$

The expected loss is:

$$
\mathbb{E}[X] = 0.80(0) + 0.10(500) + 0.08(5000) + 0.02(15000) = 750
$$

So the average annual loss is \\$750.

To measure variability:

$$
\sigma_X^2 = \sum (x - \mathbb{E}[X])^2 f(x)
$$

$$
\sigma_X^2 = 0.80(0-750)^2 + 0.10(500-750)^2 + 0.08(5000-750)^2 + 0.02(15000-750)^2
$$

$$
\sigma_X^2 = 5{,}962{,}500
$$

$$
\sigma_X = \sqrt{5{,}962{,}500} \approx 2442
$$

Even though the expected loss is only \\$750, the risk is substantial because losses of \\$5,000 or \\$15,000 are possible.

### Pooling Theorem

Let $X_1, X_2, ..., X_n$ be independent random variables, each with:

* expected value $\mu$
* variance $\sigma^2$

Let:

$$
S_n = X_1 + X_2 + \cdots + X_n
$$

Then:

$$
\mathbb{E}[S_n] = n\mu
$$

and

$$
\mathrm{Var}(S_n) = n\sigma^2
$$

So:

$$
\sigma_{S_n} = \sqrt{n}\sigma
$$

This is less than $n\sigma$, the sum of the individual standard deviations.

The **coefficient of variation** is:

$$
\mathrm{CV} = \frac{\sigma}{\mu}
$$

For the pool:

$$
\mathrm{CV}(S_n) = \frac{\sqrt{n}\sigma}{n\mu} = \frac{\sigma}{\mu\sqrt{n}}
$$

As $n$ increases, the insurer's relative risk declines.

### Example: 100 Car Owners

Suppose an insurer covers 100 car owners, each with the same loss distribution above.

For one owner:

* expected loss = \\$750
* standard deviation = \\$2,442

For 100 owners:

* expected loss = $100 \times 750 = 75,000$
* variance = $100 \times 5,962,500 = 596,250,000$
* standard deviation = $\sqrt{596,250,000} \approx 24,418$

Compare:

* sum of 100 individual standard deviations = $100 \times 2442 = 244,200$
* actual pooled standard deviation = about $24,418$

Coefficient of variation:

* one driver: $2442 / 750 = 3.26$
* pool of 100 drivers: $24,418 / 75,000 = 0.326$

Pooling makes aggregate outcomes far more predictable.

### Net Premium and Gross Premium

Insurance itself does not reduce frequency or severity of loss. It only transfers risk.

Given perfect information, the policyholder should pay:

* expected claim payments
* plus insurer expenses
* plus profit and a margin for adverse outcomes

Definitions:

* **Net premium** or **benefit premium**: expected claim payments only
* **Gross premium**: net premium plus expenses and margin

### Example: Gross Premium for the 100 Drivers

For the 100-car-owner pool:

* expected total claim payments = \\$75,000
* net premium per policy = \\$750

If the insurer adds 30% for expenses and unanticipated claims:

$$
750 \times 1.30 = 975
$$

So the **gross premium** is \\$975 per policy.

Policyholders pay more than expected loss in exchange for certainty.

## IV. CHARACTERISTICS OF AN INSURABLE RISK

For a risk to be attractive to insure:

* the potential loss must be significant enough that insurance is useful
* the loss and its financial value must be well-defined
* the policyholder should not be able to cause or manipulate the loss
* covered losses should be reasonably independent

Independence matters because correlated losses can produce many claims at once.

Example: an insurer would not want to insure every store in one area against fire if one fire could spread and damage them all.

These criteria describe an ideal insurable risk. A risk can still be insured even if it does not fully satisfy every condition, but the insurer may need extra caution or risk sharing.

## V. EXAMPLES OF INSURANCE

Common forms of insurance include:

* **Auto liability insurance**: pays for injury or property damage you cause to others
* **Collision insurance**: pays to repair or replace your car after an accident
* **Comprehensive coverage**: pays for non-collision losses such as hail or vandalism
* **Homeowners insurance**: covers damage to a home and its contents
* **Life insurance**: pays a benefit on death
* **Annuities**: provide payments while the insured is alive
* **Disability income insurance**: replaces income after disability
* **Health insurance**: helps offset medical expenses

Annuities are the complement of life insurance:

* life insurance protects against dying too soon
* annuities protect against living so long that savings are exhausted

## VI. LIMITS ON POLICY BENEFITS

Insurance policies often do not reimburse the entire loss. A policy may include:

* a maximum reimbursement
* a minimum threshold before payment begins
* reimbursement of only a percentage of each loss
* different limits for different kinds of losses

When the policyholder retains part of the loss, that is a form of **coinsurance**.

### Deductibles

A **deductible** requires the policyholder to absorb losses up to a stated amount.

If the deductible is \\$500:

* a loss less than \\$500 produces no claim payment
* a \\$2,000 loss produces a \\$1,500 claim payment

Reasons for deductibles:

1. Small losses do not trigger claim-processing expense.
2. Claim payments are reduced, lowering premiums.
3. The policyholder keeps some risk, creating incentive to avoid losses.

Potential drawbacks:

1. Policyholders may dislike not being fully reimbursed.
2. Deductibles can create misunderstanding and poor public relations.
3. Coverage may become harder to market.
4. Policyholders may overstate losses to recover the deductible.

It is important to distinguish between **losses** and **claim payments**, because with a deductible they are no longer the same.

### Example: 100 Car Owners With a \\$500 Deductible

Return to the 100-car-owner pool. If each policy has a \\$500 deductible, the claim payment distribution per policy becomes:

* $P(Y=0)=0.90$
* $P(Y=4500)=0.08$
* $P(Y=14500)=0.02$

This is because:

* no accident or a \\$500 loss both produce a \\$0 claim
* a \\$5,000 loss produces a \\$4,500 claim
* a \\$15,000 loss produces a \\$14,500 claim

Expected claim payment:

$$
\mathbb{E}[Y] = 0.90(0) + 0.08(4500) + 0.02(14500) = 650
$$

Variance:

$$
\sigma_Y^2 = 0.90(0-650)^2 + 0.08(4500-650)^2 + 0.02(14500-650)^2 = 5{,}402{,}500
$$

Standard deviation:

$$
\sigma_Y = \sqrt{5{,}402{,}500} \approx 2324
$$

For 100 policies:

* expected claim payments = \\$65,000
* variance = $540,250,000$
* standard deviation = $\sqrt{540,250,000} \approx 23,243$

Effects of the deductible:

* claim probability falls from 20% to 10%
* expected claims fall from \\$75,000 to \\$65,000
* standard deviation falls from \\$24,418 to \\$23,243

### Benefit Limits

A **benefit limit** sets the maximum amount the insurer will pay on a loss.

Reasons for benefit limits:

1. They prevent claim payments from exceeding the insurer's financial capacity.
2. They reduce the insurer's risk.
3. They let policyholders choose lower-cost coverage.

In general, lower benefit limits mean lower premiums.

Policies may also combine:

* deductibles
* maximum limits
* percentage reimbursement
* different limits for different perils

Example: a health policy may reimburse 80% of costs up to \\$5,000. If medical cost is \\$6,000, reimbursement is:

$$
0.80 \times 5000 = 4000
$$

### Example: 100 Car Owners With a \\$500 Deductible and \\$12,500 Benefit Limit

Now assume the insurer adds both:

* a \\$500 deductible
* a maximum claim payment of \\$12,500

The claim payment distribution per policy is:

$$
f_Y(y) =
\begin{cases}
0.90, & \text{loss } \le 500,\ y=0 \\
0.08, & \text{loss } = 5000,\ y=4500 \\
0.02, & \text{loss } = 15000,\ y=12500
\end{cases}
$$


Expected claim payment:

$$
\mathbb{E}[Y] = 0.90(0) + 0.08(4500) + 0.02(12500) = 610
$$

Variance:

$$
\sigma_Y^2 = 0.90(0-610)^2 + 0.08(4500-610)^2 + 0.02(12500-610)^2 = 4{,}372{,}900
$$

Standard deviation:

$$
\sigma_Y = \sqrt{4{,}372{,}900} \approx 2091
$$

For 100 policies:

* expected claim payments = \\$61,000
* variance = $437,290,000$
* standard deviation = $\sqrt{437,290,000} \approx 20,911$

With both the deductible and the limit, the insurer's expected claims fall from \\$75,000 to \\$61,000 and the standard deviation falls from \\$24,418 to \\$20,911.

## VII. INFLATION

Many policies reimburse losses at current price levels. When prices rise, claim payments also tend to rise.

However:

* deductibles are often fixed
* benefit limits are often fixed

That means inflation changes the claim payment pattern.

### Example: 100 Car Owners With a \\$500 Deductible and 10% Annual Inflation

Assume:

* deductible = \\$500
* no benefit limit
* annual inflation = 10%

Over time, the \\$5,000 and \\$15,000 losses increase with inflation, while the deductible remains fixed.

| Year | Expected Loss | Expected Claim Payment | Standard Deviation |
|:-----|--------------:|-----------------------:|-------------------:|
| 1 | 750 | 650 | 2324 |
| 2 | 825 | 725 | 2568 |
| 3 | 908 | 808 | 2836 |
| 4 | 998 | 898 | 3131 |
| 5 | 1098 | 998 | 3456 |

Observations:

* expected losses rise from 750 to 1098, a 46% increase
* expected claim payments rise from 650 to 998, a 54% increase

Because the deductible stays fixed, it becomes less important over time, so claim payments grow faster than losses.

### Example: 100 Car Owners With a \\$500 Deductible, \\$12,500 Limit, and 10% Inflation

Now add a fixed maximum claim payment of \\$12,500.

| Year | Expected Loss | Expected Claim Payment | Standard Deviation |
|:-----|--------------:|-----------------------:|-------------------:|
| 1 | 750 | 610 | 2091 |
| 2 | 825 | 655 | 2167 |
| 3 | 908 | 705 | 2257 |
| 4 | 998 | 759 | 2363 |
| 5 | 1098 | 819 | 2486 |

Observations:

* expected losses rise by 46%
* expected claim payments rise from 610 to 819, only 34%

The fixed maximum benefit offsets some inflation impact because it becomes more binding over time.

## VIII. A CONTINUOUS SEVERITY EXAMPLE

The earlier car-insurance examples used discrete loss amounts. This section uses a continuous severity model.

Consider an insurance policy that reimburses annual hospital charges for an insured individual.

Assume:

* probability of hospitalization in a year: $P(H=1)=0.15$
* if hospitalized, charges $X$ have density:

$$
f_X(x \mid H=1) = 0.1e^{-0.1x}, \quad x > 0
$$

### Example: One Individual's Hospital Charges

Expected value:

$$
\mathbb{E}[X] = 1.5
$$

Second moment:

$$
\mathbb{E}[X^2] = 30
$$

Variance:

$$
\sigma_X^2 = 30 - (1.5)^2 = 27.75
$$

Standard deviation:

$$
\sigma_X = \sqrt{27.75} \approx 5.27
$$

Coefficient of variation:

$$
\frac{\sigma_X}{\mathbb{E}[X]} = \frac{5.27}{1.5} \approx 3.51
$$

### Example: Pool of 200 Individuals

Let:

$$
S = \sum_{i=1}^{200} X_i
$$

Then:

$$
\mathbb{E}[S] = 200(1.5) = 300
$$

$$
\sigma_S^2 = 200(27.75) = 5550
$$

$$
\sigma_S = \sqrt{5550} \approx 74.50
$$

Coefficient of variation:

$$
\frac{74.50}{300} \approx 0.25
$$

Again, pooling sharply reduces relative variability.

### Example: Pool of 200 Individuals With Deductible 5

Now suppose the insurer reimburses annual hospital charges with a deductible of 5 per individual.

Let:

$$
Y = \max(0, X - 5)
$$

From the study note:

$$
\mathbb{E}[Y] = 0.91
$$

$$
\mathbb{E}[Y^2] = 18.20
$$

$$
\sigma_Y^2 = 18.20 - (0.91)^2 = 17.37
$$

$$
\sigma_Y = \sqrt{17.37} \approx 4.17
$$

For the pool of 200 individuals:

$$
\mathbb{E}[S_Y] = 200(0.91) = 182
$$

$$
\sigma_{S_Y}^2 = 200(17.37) = 3474
$$

$$
\sigma_{S_Y} = \sqrt{3474} \approx 58.94
$$

### Example: Pool of 200 Individuals With Deductible 5 and 80% Coinsurance

If the insurer reimburses only 80% of charges above the deductible:

$$
\mathbb{E}[0.8S_Y] = 0.8(182) = 146
$$

$$
\sigma_{0.8S_Y}^2 = (0.8)^2(3474) \approx 2223
$$

$$
\sigma_{0.8S_Y} = 0.8(58.94) \approx 47.15
$$

Deductibles and coinsurance reduce both expected claim payments and volatility.

## IX. THE ROLE OF THE ACTUARY

Actuaries combine mathematical, statistical, and business skills to estimate expected costs and risks in situations involving financial uncertainty.

In insurance, that includes:

* estimating frequency and severity distributions
* combining them into a loss distribution
* adjusting for policy provisions such as deductibles and limits
* determining net premiums and gross premiums
* determining the amount of assets needed to pay claims and expenses
* projecting cash flows over time

Actuaries usually begin with past data. They try to use data from the actual insurance pool or from a comparable population.

Example: if pricing health coverage for active workers, the actuary would not want to rely on data from disabled or retired populations.

Actuaries also need to judge whether past data is a good guide to the future. The more data available, the more reliable the estimate tends to be.

### Example: Estimating Mortality Probability

Suppose an actuary wants to estimate the probability that a 70-year-old woman dies within one year.

The actuary:

* collects a large random sample of 70-year-old women from previous years
* calculates the proportion who died within one year

By the Central Limit Theorem, if the underlying probability is $p$, then the sample mean is approximately normal with:

* mean $p$
* standard deviation proportional to $1/\sqrt{n}$

So larger samples reduce estimation uncertainty.

Actuaries must also account for structural change. For example:

* new medical treatments may increase healthcare costs
* inflation may affect claim amounts
* investment returns may affect long-term pricing and reserving

They also help project profitability, solvency, and the impact of new products.

## X. CONCLUSION

This topic is a foundation for actuarial work. The examples in this post focus on insurance, but the underlying ideas apply to many settings involving uncertain financial outcomes.

Key ideas to keep in mind:

* expected value measures average cost, not total risk
* standard deviation captures uncertainty around that average
* pooling reduces relative variability
* deductibles, limits, and coinsurance reshape claim payments
* inflation can materially alter results when policy provisions stay fixed
* actuaries turn these concepts into pricing, reserving, and risk-management decisions

This is why risk and insurance sits at the core of actuarial modeling.
