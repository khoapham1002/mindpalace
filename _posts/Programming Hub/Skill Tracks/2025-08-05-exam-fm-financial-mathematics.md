---
layout: post
title: Learn Exam FM - Financial Mathematics
date: 2025-08-05 19:09 -0700
description: Exam FM Study Guide
authors: [khoa_pham]
categories: [Programming Hub, Skill Tracks]
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

### 2. More General Annuities


## C. Yield Rates

### 1. Yield Rates


## D. Amortization Schedules

### 1. Amortization Schedules


## E. Bonds and Other Securities

### 1. Bonds and Other Securities


## F. Interest Rate Behavior

### 1. Term Structure of Interest Rates


## G. Duration, Convexity and Immunization

### 1. Duration

### 2. Convexity

### 3. Immunization
