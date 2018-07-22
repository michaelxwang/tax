### IRS underpayment penalty and how to avoid it

Generally speaking, you need to pay estimated tax every quarter.
If you did not pay enough, then you will pay "estimated tax penalty",
this is what line 79 of [form 1040
](https://www.irs.gov/pub/irs-pdf/f1040.pdf) is for.

Although it is called "penalty", it is essentially an interest on
the late payment. The interest rate on each quarter is determined
by the [federal short-term
rate](https://apps.irs.gov/app/picklist/list/federalRates.html) in
the first month of the previous quarter, rounded to the nearest
integer, plus 3%. For example, the federal short term rate in
October 2017 is 1.27%, so the interest for the first quarter 2018
is `ROUND(1.27%) + 3% = 4%`. In the same way, we can derive the
interest rates for the rest of three quarters of 2018 are 5%.

To provide an estimate for the amount of underpayment penalty, let
us assume the income, estimated tax payment are the same for each
quarter, the weighted average of annual interest rate is:

```
R(2018) = (12/12 * 4% + 10/12 * 5% + 7/12 *5% + 3/12 * 5%) / 4 = 3.08%
```

which means you pay about 3% for 2018 on the shortage to required
tax payment, which is the lesser of 90% of the current year's tax
or (100%|110%) of last year's tax (with details below for 100% vs 110%).

Even the penalty is not a huge amount, it is better to avoid it.
The penalty will not apply if you satisfy either of the following
conditions (see [form 2210](https://www.irs.gov/pub/irs-pdf/f2210.pdf)
and [form 2210 instruction](https://www.irs.gov/pub/irs-pdf/f1040.pdf)):

- `The withholding > current year tax * 90%`
- `The withholding > current year tax - $1,000`
- `The withholding > last year's tax * X`, where `X = 110%` if the
adjusted gross income on your previous year's return is over $150,000,
or over $75,000 if you are married filing separately, otherwise `X = 100%`.
- You had no tax liability for prior year and you were a U.S. citizen
or resident alien for the entire year.

The first two condition is hard to follow as it request to know the
current year's tax which you don't until you complete the return.
On the other hand, all the numbers are known for the third condition:
the previous tax year is on the last year's form 1040, in general
we can use line 61 but for special situations, please see [form
2210 instruction](https://www.irs.gov/pub/irs-pdf/f1040.pdf) for
details; the withholding is on your pay check stub and can be easily
extrapolated to the end of year. If you expect you won't satisfy
the third condition, and are worried about the penalty, you can use
form [w4](https://www.irs.gov/pub/irs-pdf/fw4.pdf) to make a one
time additional payment.

The third condition is a sufficient condition, not a necessary
condition. That is, if this condition is satisfied, then there
will no penalty. For example, a million dollars capital gain without
tax paid, you just need to pay the tax owed by the due date without
penalty. However, if it is not satisfied, it does not mean the
penalty will apply. There will be no penalty still if either of
the first two conditions are satisfied which we do not know until
we prepare the return for the current year.

The third condition does not work well if you had a million dollars
additional income in previous year, but not in current year. It
still works just not well. Also this condition applies to _withholding_
only, not estimated payment made on
[1040-ES](https://www.irs.gov/pub/irs-pdf/f1040es.pdf).

The states have similar conditions to avoid penalties, for example,
you do not pay penalty for
[VA](https://tax.virginia.gov/sites/default/files/vatax-pdf/2017-form-760c-instructions.pdf)
if you satisfy the following conditions:

- You have paid 90% of the tax you owe, or the tax owed is less than $150, for the current year.
- You have paid 100% (always 100% regardless of your income) of the tax you owed for the previous tax year.

```
Michael Wang, EA
Admitted to Practice Before the IRS.
Tax Professional Since 2005, All States.
Tax Return Over Cloud
mwang@unixlabplus.com
Wechat ID: puravidawechat
```
