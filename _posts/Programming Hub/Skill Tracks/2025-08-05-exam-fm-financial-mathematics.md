---
layout: post
title: Learn Exam FM - Financial Mathematics
date: 2025-08-05 19:09 -0700
description: Exam FM Study Guide
authors: [khoa_pham]
categories: [Programming Hub, Skill Tracks]
tags: [actuarial]
pin: false
math: true
mermaid: true
toc: true
comments: true
---


## A. Basics of Interest

### 1. Measurement of Interest

#### 1) Interest Accumulation - Part 1

The accumulation function $$a(t)$$ measures the value at time $$t$$ of one unit invested at time $$0$$.

Usually:

$$
a(0) = 1
$$

If $$k$$ is invested at time $$0$$, then the accumulated value at time $$t$$ is:

$$
A(t) = k a(t)
$$

The amount of interest earned from time $$s$$ to time $$t$$ is:

$$
A(t) - A(s)
$$

The effective rate of interest over the interval from $$s$$ to $$t$$ is:

$$
i_{s,t}
=
\frac{A(t) - A(s)}{A(s)}
=
\frac{a(t) - a(s)}{a(s)}
$$

So:

$$
A(t) = A(s)(1 + i_{s,t})
$$

#### 2) Interest Accumulation - Part 2

For one period, the effective annual rate of interest is:

$$
i = a(1) - 1
$$

If the effective rate of interest is constant each year, then:

$$
a(t) = (1 + i)^t
$$

For integer $$n$$:

$$
A(n) = A(0)(1 + i)^n
$$

Interest earned during year $$n$$ is:

$$
I_n = A(n) - A(n - 1)
$$

Under compound interest:

$$
I_n = A(0)(1 + i)^{n - 1}i
$$

#### 3) Present Value - Part 1

Present value discounts a future payment back to an earlier time.

If $$C$$ is paid at time $$t$$, then its present value at time $$0$$ is:

$$
PV = \frac{C}{a(t)}
$$

Under compound interest:

$$
PV = C(1 + i)^{-t}
$$

The discount factor is:

$$
v = \frac{1}{1 + i}
$$

So:

$$
PV = Cv^t
$$

#### 4) Present Value - Part 2

The effective rate of discount $$d$$ measures discount as a percentage of the amount due at the end of the period.

For one period:

$$
d = \frac{i}{1 + i}
$$

Equivalently:

$$
d = 1 - v
$$

Useful conversions:

$$
v = 1 - d
$$

$$
i = \frac{d}{1 - d}
$$

$$
d = \frac{i}{1 + i}
$$

#### 5) Compound Interest

Under compound interest:

$$
a(t) = (1 + i)^t
$$

Accumulated value:

$$
AV = PV(1 + i)^t
$$

Present value:

$$
PV = AV(1 + i)^{-t} = AVv^t
$$

For a cash flow $$C_k$$ paid at time $$t_k$$, its value at time $$T$$ is:

$$
C_k(1 + i)^{T - t_k}
$$

The value at time $$T$$ of several cash flows is:

$$
\sum_k C_k(1 + i)^{T - t_k}
$$

#### 6) Simple Interest

Under simple interest:

$$
a(t) = 1 + it
$$

Accumulated value:

$$
AV = PV(1 + it)
$$

Present value:

$$
PV = \frac{AV}{1 + it}
$$

Simple interest does not compound. Interest grows linearly with time:

$$
I = Pit
$$

Simple discount uses:

$$
PV = AV(1 - dt)
$$

So the simple-discount accumulation function is:

$$
a(t) = \frac{1}{1 - dt}
$$

where $$dt < 1$$.

#### 7) Nominal Annual Rates of Interest

A nominal annual rate of interest convertible $$m$$ times per year is written:

$$
i^{(m)}
$$

The periodic rate is:

$$
\frac{i^{(m)}}{m}
$$

The effective annual rate is:

$$
1 + i =
\left(1 + \frac{i^{(m)}}{m}\right)^m
$$

So:

$$
i =
\left(1 + \frac{i^{(m)}}{m}\right)^m - 1
$$

Solving for the nominal rate:

$$
i^{(m)}
=
m\left[(1 + i)^{1/m} - 1\right]
$$

#### 8) Nominal Annual Rates of Discount

A nominal annual rate of discount convertible $$m$$ times per year is written:

$$
d^{(m)}
$$

The periodic discount rate is:

$$
\frac{d^{(m)}}{m}
$$

The annual discount factor is:

$$
v =
\left(1 - \frac{d^{(m)}}{m}\right)^m
$$

So:

$$
1 + i =
\left(1 - \frac{d^{(m)}}{m}\right)^{-m}
$$

and:

$$
i =
\left(1 - \frac{d^{(m)}}{m}\right)^{-m} - 1
$$

Solving for the nominal discount rate:

$$
d^{(m)}
=
m\left[1 - v^{1/m}\right]
$$

#### 9) Force of Interest - Part 1

The force of interest $$\delta_t$$ is the instantaneous rate of growth of the accumulation function.

$$
\delta_t = \frac{a'(t)}{a(t)}
$$

Equivalently:

$$
\delta_t = \frac{d}{dt}\ln a(t)
$$

Therefore:

$$
a(t) =
e^{\int_0^t \delta_s \, ds}
$$

For an amount function $$A(t)$$:

$$
\delta_t = \frac{A'(t)}{A(t)}
$$

#### 10) Force of Interest - Part 2

If the force of interest is constant, then:

$$
\delta_t = \delta
$$

and:

$$
a(t) = e^{\delta t}
$$

The relationship with the effective annual interest rate is:

$$
1 + i = e^\delta
$$

So:

$$
\delta = \ln(1 + i)
$$

Since $$v = \frac{1}{1 + i}$$:

$$
\delta = -\ln v
$$

Continuous compounding is the limiting case of nominal interest:

$$
\lim_{m \to \infty}
\left(1 + \frac{i^{(m)}}{m}\right)^m
=
e^\delta
$$

### 2. Solution of Problems in Interest

#### 1) The Basic Problem

Most interest problems are built from the same equation:

$$
\text{Value at comparison date}
=
\sum_k C_k \cdot \text{accumulation/discount factor}
$$

Under compound interest, the value at time $$T$$ of cash flows $$C_k$$ paid at times $$t_k$$ is:

$$
\sum_k C_k(1 + i)^{T - t_k}
$$

If $$T - t_k$$ is negative, the factor discounts instead of accumulates.

#### 2) Equations of Value

An equation of value compares two sets of cash flows at the same focal date.

At focal date $$T$$:

$$
\sum_j A_j(1 + i)^{T - s_j}
=
\sum_k B_k(1 + i)^{T - t_k}
$$

where $$A_j$$ are one set of payments and $$B_k$$ are the other set.

The focal date can be any date when the same interest model is used consistently.

#### 3) Unknown Time

For a single investment growing from $$PV$$ to $$AV$$ under compound interest:

$$
AV = PV(1 + i)^t
$$

Solving for time:

$$
t =
\frac{\ln(AV/PV)}{\ln(1 + i)}
$$

Under simple interest:

$$
AV = PV(1 + it)
$$

So:

$$
t =
\frac{AV/PV - 1}{i}
$$

#### 4) Unknown Rate of Interest

For a single compound-interest cash flow:

$$
AV = PV(1 + i)^t
$$

Solving for the effective interest rate:

$$
i =
\left(\frac{AV}{PV}\right)^{1/t} - 1
$$

For multiple cash flows, the unknown rate usually comes from an equation of value:

$$
\sum_k C_k(1 + i)^{-t_k} = 0
$$

This equation may need numerical solving.


## B. Annuities

### 1. Basic Annuities

#### 1) Annuity-Immediate - Present Value

An annuity-immediate pays at the end of each period.

For payments of $$1$$ at times $$1, 2, \dots, n$$:

$$
a_{\overline{n}|}
=
v + v^2 + \cdots + v^n
$$

Using the geometric series:

$$
a_{\overline{n}|}
=
\frac{1 - v^n}{i}
$$

For payments of $$R$$:

$$
PV = R a_{\overline{n}|}
$$

#### 2) Annuity-Immediate - Useful Tools

Useful identities:

$$
1 - v^n = i a_{\overline{n}|}
$$

$$
a_{\overline{n}|}
=
v a_{\overline{n-1}|} + v
$$

$$
a_{\overline{n}|}
=
a_{\overline{k}|}
+ v^k a_{\overline{n-k}|}
$$

A deferred annuity-immediate with payments from time $$m+1$$ through time $$m+n$$ has present value:

$$
v^m a_{\overline{n}|}
$$

#### 3) Annuity-Immediate - Accumulated Value

The accumulated value at time $$n$$ of payments of $$1$$ at times $$1, 2, \dots, n$$ is:

$$
s_{\overline{n}|}
=
1 + (1+i) + \cdots + (1+i)^{n-1}
$$

So:

$$
s_{\overline{n}|}
=
\frac{(1+i)^n - 1}{i}
$$

Relation between present value and accumulated value:

$$
s_{\overline{n}|}
=
(1+i)^n a_{\overline{n}|}
$$

For payments of $$R$$:

$$
AV = R s_{\overline{n}|}
$$

#### 4) Annuity-Due - Present Value

An annuity-due pays at the beginning of each period.

For payments of $$1$$ at times $$0, 1, \dots, n-1$$:

$$
\ddot{a}_{\overline{n}|}
=
1 + v + \cdots + v^{n-1}
$$

So:

$$
\ddot{a}_{\overline{n}|}
=
(1+i)a_{\overline{n}|}
$$

Also:

$$
\ddot{a}_{\overline{n}|}
=
\frac{1 - v^n}{d}
$$

For payments of $$R$$:

$$
PV = R\ddot{a}_{\overline{n}|}
$$

#### 5) Annuity-Due - Accumulated Value

The accumulated value at time $$n$$ of payments of $$1$$ at times $$0, 1, \dots, n-1$$ is:

$$
\ddot{s}_{\overline{n}|}
=
(1+i)s_{\overline{n}|}
$$

Also:

$$
\ddot{s}_{\overline{n}|}
=
\frac{(1+i)^n - 1}{d}
$$

For payments of $$R$$:

$$
AV = R\ddot{s}_{\overline{n}|}
$$

#### 6) Annuity-Immediate vs. Annuity-Due

Each annuity-due payment is made one period earlier than the corresponding annuity-immediate payment.

Therefore:

$$
\ddot{a}_{\overline{n}|}
=
(1+i)a_{\overline{n}|}
$$

and:

$$
\ddot{s}_{\overline{n}|}
=
(1+i)s_{\overline{n}|}
$$

Equivalently:

$$
a_{\overline{n}|}
=
v\ddot{a}_{\overline{n}|}
$$

$$
s_{\overline{n}|}
=
v\ddot{s}_{\overline{n}|}
$$

#### 7) Basic Annuities - Miscellaneous

A perpetuity-immediate pays forever at the end of each period.

$$
a_{\overline{\infty}|}
=
\frac{1}{i}
$$

A perpetuity-due pays forever at the beginning of each period.

$$
\ddot{a}_{\overline{\infty}|}
=
\frac{1}{d}
$$

A deferred perpetuity-immediate beginning after $$m$$ periods has present value:

$$
\frac{v^m}{i}
$$

#### 8) Perpetuities

For a level perpetuity-immediate with payment $$R$$:

$$
PV = \frac{R}{i}
$$

For a level perpetuity-due with payment $$R$$:

$$
PV = \frac{R}{d}
$$

For a perpetuity with first payment $$R$$ at time $$k$$:

$$
PV = Rv^{k-1}a_{\overline{\infty}|}
=
\frac{Rv^{k-1}}{i}
$$

### 2. More General Annuities

#### 1) Annuities Payable m-thly

For an annuity-immediate payable $$m$$ times per year, with total annual payment $$1$$, each payment is:

$$
\frac{1}{m}
$$

The present value over $$n$$ years is:

$$
a_{\overline{n}|}^{(m)}
=
\frac{1 - v^n}{i^{(m)}}
$$

The accumulated value is:

$$
s_{\overline{n}|}^{(m)}
=
\frac{(1+i)^n - 1}{i^{(m)}}
$$

For an annuity-due payable $$m$$ times per year:

$$
\ddot{a}_{\overline{n}|}^{(m)}
=
\frac{1 - v^n}{d^{(m)}}
$$

$$
\ddot{s}_{\overline{n}|}^{(m)}
=
\frac{(1+i)^n - 1}{d^{(m)}}
$$

#### 2) Increasing Annuities - Arithmetic

For an increasing annuity-immediate with payments:

$$
1, 2, 3, \dots, n
$$

at times $$1, 2, 3, \dots, n$$:

$$
(Ia)_{\overline{n}|}
=
v + 2v^2 + 3v^3 + \cdots + nv^n
$$

Formula:

$$
(Ia)_{\overline{n}|}
=
\frac{a_{\overline{n}|} - nv^n}{i}
$$

For payments increasing by $$Q$$ each period, multiply the increasing part by $$Q$$.

#### 3) Decreasing Annuities - Arithmetic

For a decreasing annuity-immediate with payments:

$$
n, n-1, n-2, \dots, 1
$$

at times $$1, 2, 3, \dots, n$$:

$$
(Da)_{\overline{n}|}
=
nv + (n-1)v^2 + \cdots + v^n
$$

Formula:

$$
(Da)_{\overline{n}|}
=
\frac{n - a_{\overline{n}|}}{i}
$$

Increasing and decreasing annuities combine to a level annuity:

$$
(Ia)_{\overline{n}|} + (Da)_{\overline{n}|}
=
(n+1)a_{\overline{n}|}
$$

#### 4) Varying Annuities - Geometric - Part 1

For payments growing geometrically:

$$
1, 1+g, (1+g)^2, \dots, (1+g)^{n-1}
$$

at times $$1, 2, \dots, n$$, the present value is:

$$
PV =
\sum_{k=1}^n (1+g)^{k-1}v^k
$$

If $$i \ne g$$:

$$
PV =
\frac{1 - \left(\frac{1+g}{1+i}\right)^n}{i - g}
$$

If $$i = g$$:

$$
PV =
\frac{n}{1+i}
$$

#### 5) Varying Annuities - Geometric - Part 2

For first payment $$R$$ at time $$1$$:

$$
PV =
R
\frac{1 - \left(\frac{1+g}{1+i}\right)^n}{i - g}
$$

where $$i \ne g$$.

For a growing perpetuity-immediate:

$$
PV =
\frac{R}{i - g}
$$

where $$i > g$$.

The accumulated value at time $$n$$ is:

$$
AV = PV(1+i)^n
$$

#### 6) Continuous Annuities - Part 1

A continuous annuity pays continuously over time.

For a level continuous payment stream of rate $$1$$ per year over $$n$$ years:

$$
\overline{a}_{\overline{n}|}
=
\int_0^n v^t \, dt
$$

With constant force of interest $$\delta$$:

$$
\overline{a}_{\overline{n}|}
=
\frac{1 - v^n}{\delta}
$$

The accumulated value is:

$$
\overline{s}_{\overline{n}|}
=
\frac{(1+i)^n - 1}{\delta}
$$

#### 7) Continuous Annuities - Part 2

For a continuous perpetuity with payment rate $$R$$:

$$
PV =
\int_0^\infty Rv^t \, dt
=
\frac{R}{\delta}
$$

For a continuous payment stream with rate $$r(t)$$:

$$
PV =
\int_0^n r(t)v^t \, dt
$$

Accumulated value at time $$n$$:

$$
AV =
\int_0^n r(t)(1+i)^{n-t} \, dt
$$

#### 8) Annuity Tricks

When payments are shifted in time, factor out the shift.

For example:

$$
v^m a_{\overline{n}|}
$$

means a level annuity-immediate deferred $$m$$ periods.

When payments are split into level and varying pieces:

$$
\text{Payment}_k = \text{level part} + \text{increasing part}
$$

Then:

$$
PV =
PV(\text{level part})
+
PV(\text{increasing part})
$$

Use a focal date that makes the cash flows easiest to compare.


## C. Yield Rates

### 1. Yield Rates

#### 1) Net Present Value and Internal Rate of Return

For cash flows $$C_0, C_1, \dots, C_n$$ at times $$0, 1, \dots, n$$, the net present value at rate $$i$$ is:

$$
NPV(i)
=
\sum_{k=0}^n C_k v^k
=
\sum_{k=0}^n C_k(1+i)^{-k}
$$

The internal rate of return is a rate $$i$$ satisfying:

$$
NPV(i) = 0
$$

Equivalently:

$$
\sum_{k=0}^n C_k(1+i)^{-k} = 0
$$

If there is more than one sign change in the cash flows, there may be more than one IRR.

#### 2) Reinvestment Rates

If interim payments are reinvested at rate $$j$$ through time $$n$$, the accumulated value is:

$$
AV =
\sum_{k=0}^n C_k(1+j)^{n-k}
$$

The yield rate $$i$$ over the full investment period satisfies:

$$
\text{initial investment}(1+i)^n = AV
$$

So:

$$
i =
\left(\frac{AV}{\text{initial investment}}\right)^{1/n} - 1
$$

When reinvestment is part of the problem, separate:

$$
\text{investment yield}
\quad \text{and} \quad
\text{reinvestment yield}
$$

#### 3) Yield Rates

The yield rate is the interest rate that makes the value of inflows equal to the value of outflows.

At time $$0$$:

$$
\sum \text{outflows} \cdot v^{t}
=
\sum \text{inflows} \cdot v^{t}
$$

For a purchase price $$P$$ and future receipts $$C_k$$:

$$
P =
\sum_k C_k(1+i)^{-t_k}
$$

The yield rate is usually solved numerically when the cash-flow pattern is not a simple annuity.


## D. Amortization Schedules

### 1. Amortization Schedules

#### 1) Amortization Schedule - Part 1

A loan is amortized when payments repay both interest and principal.

For a loan amount $$L$$ repaid with level payments $$R$$ at the end of each period:

$$
L = R a_{\overline{n}|}
$$

So:

$$
R =
\frac{L}{a_{\overline{n}|}}
$$

At payment $$k$$:

$$
\text{interest portion} = iB_{k-1}
$$

$$
\text{principal portion} = R - iB_{k-1}
$$

where $$B_{k-1}$$ is the outstanding balance immediately after payment $$k-1$$.

#### 2) Amortization Schedule - Part 2

The outstanding balance recursion is:

$$
B_k = B_{k-1}(1+i) - R
$$

The prospective method looks forward:

$$
B_k =
R a_{\overline{n-k}|}
$$

The retrospective method accumulates the original loan and subtracts accumulated payments:

$$
B_k =
L(1+i)^k - R s_{\overline{k}|}
$$

These methods give the same balance when the loan is amortized as scheduled.

#### 3) Drop Payment vs. Balloon Payment

A drop payment is a final payment smaller than the regular level payment.

If $$m$$ full payments of $$R$$ have been made, the remaining balance is:

$$
B_m = L(1+i)^m - R s_{\overline{m}|}
$$

The drop payment one period later is:

$$
B_m(1+i)
$$

A balloon payment is a final payment larger than the regular level payment.

If a loan balance $$B_m$$ remains after payment $$m$$, the balloon payment at time $$m+r$$ is:

$$
B_m(1+i)^r
$$


## E. Bonds and Other Securities

### 1. Bonds and Other Securities

#### 1) Types of Securities

A bond usually has:

$$
F = \text{face value}
$$

$$
C = \text{redemption value}
$$

$$
r = \text{coupon rate}
$$

$$
i = \text{yield rate}
$$

For annual coupons, the coupon payment is:

$$
Fr
$$

For coupons paid $$m$$ times per year, each coupon is:

$$
\frac{Fr}{m}
$$

#### 2) Price of a Bond

The price of a bond is the present value of its coupons plus the present value of its redemption value.

For annual coupons over $$n$$ years:

$$
P =
Fr a_{\overline{n}|}
+
Cv^n
$$

For coupons paid $$m$$ times per year over $$n$$ years:

$$
P =
\frac{Fr}{m}
\frac{1 - (1+j)^{-mn}}{j}
+
C(1+j)^{-mn}
$$

where $$j$$ is the effective yield rate per coupon period.

If the yield is quoted nominally convertible $$m$$ times per year:

$$
j = \frac{i^{(m)}}{m}
$$

#### 3) Premium and Discount Bonds

If a bond price is greater than its redemption value, the bond is bought at a premium:

$$
P > C
$$

If a bond price is less than its redemption value, the bond is bought at a discount:

$$
P < C
$$

For a bond redeemed at par:

$$
\text{coupon rate} > \text{yield rate}
\quad \Rightarrow \quad
\text{premium bond}
$$

$$
\text{coupon rate} < \text{yield rate}
\quad \Rightarrow \quad
\text{discount bond}
$$

When coupon rate equals yield rate:

$$
P = C
$$

#### 4) Bond Amortization

The book value after $$k$$ coupon payments is the present value of the remaining coupons and redemption value.

For annual coupons:

$$
B_k =
Fr a_{\overline{n-k}|}
+
Cv^{n-k}
$$

Interest earned during period $$k$$ is:

$$
iB_{k-1}
$$

The coupon received is:

$$
Fr
$$

The amortization of premium is:

$$
Fr - iB_{k-1}
$$

For a discount bond, the book value increases by:

$$
iB_{k-1} - Fr
$$

#### 5) Callable Bonds

A callable bond may be redeemed early by the issuer.

For each possible call date, compute:

$$
\text{price at issue}
=
PV(\text{coupons until call date})
+
PV(\text{call price})
$$

The issuer tends to call when doing so is financially favorable to the issuer.

For investor yield analysis, compare yields across possible redemption dates and identify the conservative scenario required by the problem.


## F. Interest Rate Behavior

### 1. Term Structure of Interest Rates

#### 1) Yield Curves

A yield curve shows the relationship between yield rate and time to maturity.

Common shapes:

$$
\text{increasing}, \quad
\text{decreasing}, \quad
\text{flat}, \quad
\text{humped}
$$

The yield for a term of $$n$$ years may be written:

$$
i_n
$$

When rates vary by term, do not use a single flat interest rate unless the problem says to.

#### 2) Spot Rates

The $$n$$-year spot rate $$s_n$$ is the yield on a zero-coupon bond maturing at time $$n$$.

The price at time $$0$$ of a payment of $$1$$ at time $$n$$ is:

$$
P(0,n) =
\frac{1}{(1+s_n)^n}
$$

So:

$$
P(0,n) = v_n^n
$$

where:

$$
v_n = \frac{1}{1+s_n}
$$

For a cash flow $$C_n$$ paid at time $$n$$:

$$
PV = C_n(1+s_n)^{-n}
$$

#### 3) Forward Rates

A forward rate is an interest rate implied today for a future period.

Let $$f_{m,n}$$ be the annual effective forward rate from time $$m$$ to time $$n$$.

Then:

$$
(1+s_n)^n
=
(1+s_m)^m(1+f_{m,n})^{n-m}
$$

So:

$$
1+f_{m,n}
=
\left[
\frac{(1+s_n)^n}{(1+s_m)^m}
\right]^{1/(n-m)}
$$

For a one-year forward rate from time $$k-1$$ to time $$k$$:

$$
1+f_{k-1,k}
=
\frac{(1+s_k)^k}{(1+s_{k-1})^{k-1}}
$$

#### 4) Real Rates of Interest

The nominal interest rate combines real growth and inflation.

Let:

$$
i = \text{nominal interest rate}
$$

$$
r = \text{real interest rate}
$$

$$
h = \text{inflation rate}
$$

Then:

$$
1+i = (1+r)(1+h)
$$

Solving for the real rate:

$$
r =
\frac{1+i}{1+h} - 1
$$

Equivalently:

$$
r =
\frac{i-h}{1+h}
$$


## G. Duration, Convexity and Immunization

### 1. Duration

#### 1) Price as a Function of Yield

For cash flows $$C_t$$ paid at times $$t$$, the price as a function of yield $$i$$ is:

$$
P(i) =
\sum_t C_t(1+i)^{-t}
$$

Using $$v = (1+i)^{-1}$$:

$$
P(i) =
\sum_t C_t v^t
$$

As yield increases, price decreases.

#### 2) Macaulay Duration

Macaulay duration is the present-value-weighted average payment time.

Let:

$$
w_t =
\frac{C_t v^t}{P}
$$

Then:

$$
\sum_t w_t = 1
$$

Macaulay duration is:

$$
D_{\text{Mac}}
=
\sum_t t w_t
=
\frac{\sum_t t C_t v^t}{P}
$$

For a zero-coupon bond maturing at time $$n$$:

$$
D_{\text{Mac}} = n
$$

#### 3) Modified Duration - Part 1

Modified duration measures price sensitivity to a change in yield.

For annual effective yield:

$$
D_{\text{mod}}
=
\frac{D_{\text{Mac}}}{1+i}
$$

Also:

$$
D_{\text{mod}}
=
-\frac{P'(i)}{P(i)}
$$

The first-order price approximation is:

$$
\frac{\Delta P}{P}
\approx
-D_{\text{mod}}\Delta i
$$

#### 4) Modified Duration - Part 2

If yield is quoted convertible $$m$$ times per year, with periodic rate:

$$
j = \frac{i^{(m)}}{m}
$$

then duration measured in coupon periods must be converted consistently.

For a change in the periodic yield:

$$
\frac{\Delta P}{P}
\approx
-D_{\text{mod, period}}\Delta j
$$

For a change in the nominal annual yield:

$$
\Delta j = \frac{\Delta i^{(m)}}{m}
$$

The key is to match:

$$
\text{cash-flow timing}, \quad
\text{yield period}, \quad
\text{yield change}
$$

#### 5) Portfolios and Passage of Time

For a portfolio with assets indexed by $$k$$:

$$
P = \sum_k P_k
$$

Portfolio Macaulay duration is the market-value-weighted average:

$$
D_P =
\sum_k
\frac{P_k}{P}D_k
$$

For liabilities:

$$
D_L =
\sum_k
\frac{PV(L_k)}{PV(L)}t_k
$$

After time passes, recompute duration using the remaining cash flows and the new valuation date.

#### 6) Approximation Using Duration

For a small change in yield:

$$
P(i + \Delta i)
\approx
P(i)\left(1 - D_{\text{mod}}\Delta i\right)
$$

So:

$$
\Delta P
\approx
-P(i)D_{\text{mod}}\Delta i
$$

Duration is a linear approximation, so it is less accurate for large yield changes.

### 2. Convexity

#### 1) Convexity

Convexity improves the duration approximation by adding curvature.

The modified convexity is:

$$
C_{\text{mod}}
=
\frac{P''(i)}{P(i)}
$$

For annual effective yield:

$$
C_{\text{mod}}
=
\frac{
\sum_t t(t+1)C_t v^{t+2}
}{
P
}
$$

Second-order price approximation:

$$
\frac{\Delta P}{P}
\approx
-D_{\text{mod}}\Delta i
+
\frac{1}{2}C_{\text{mod}}(\Delta i)^2
$$

#### 2) Macaulay Convexity and Portfolios

Macaulay convexity is a present-value-weighted average of squared payment times:

$$
C_{\text{Mac}}
=
\sum_t t^2 w_t
$$

where:

$$
w_t =
\frac{C_t v^t}{P}
$$

Portfolio convexity is the market-value-weighted average of component convexities:

$$
C_P =
\sum_k
\frac{P_k}{P}C_k
$$

Higher convexity generally means the asset price benefits more from large yield movements, all else equal.

### 3. Immunization

#### 1) Redington Immunization

Redington immunization matches assets and liabilities at the valuation yield.

At the chosen yield rate:

$$
PV_A = PV_L
$$

Durations match:

$$
D_A = D_L
$$

Asset convexity exceeds liability convexity:

$$
C_A > C_L
$$

These conditions make the surplus:

$$
PV_A - PV_L
$$

locally protected against small yield changes.

#### 2) Full Immunization and Dedication

Full immunization is stronger than Redington immunization. It requires assets to cover liabilities across a range of yield changes, not only locally.

Dedication, or cash-flow matching, chooses assets so that asset cash flows meet liability cash flows directly.

For each liability date $$t$$:

$$
\text{asset cash flow at } t
\ge
\text{liability cash flow at } t
$$

Cash-flow matching reduces reinvestment and liquidation risk, but it may require a larger or less flexible asset portfolio.
