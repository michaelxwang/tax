## Math in tax code - depreciation formula

Over the years I have been amazed by the amount of math used in tax
laws, and some of them are complicated math. We have been talking about
depreciation for years, and we know there are percentage applied each
corresponding to the life of the property, and other variables, but have
you seen a literature where the actual percentages are derived? I have
not, and the purpose of this article is to derive math formulas used in
IRS tables.

First a little background on the tax rules.

When you purchase a major item for your business such as a printer that
can last for multiple years, you cannot deduct the full amount of cost
in the first year, but instead you should deduct a portion of the cost
for multiple years, this process is called depreciation.

The current tax depreciation system used in the United States is Modified
Accelerated Cost Recovery System, or [MACRS](https://en.wikipedia.org/wiki/MACRS). Almost everyone uses
the extensive tables in [IRS Publication 946](https://www.irs.gov/pub/irs-pdf/p946.pdf), a 120-page document,
or computer software to to compute the depreciation amount, but we will
see how these numbers come out.

The percentage you can use to depreciate depends on:

- Life: the number of years (Y) the property can last. It does not matter
how long it actually lasts, IRS says it last N years, then you need to
depreciate for N years.

- Declining balance rate: the multiplying factor (D) on the straight line rate (1/Y).
Therefore the depreciation amount is `D * 1/Y` over the remaining cost basis (the total cost basis less the accumulated depreciation in previous years).

- Convention: the discount for the first year. With half year (HY)
convention, the first year depreciation rate is reduced by 50%, as well
as the last year as if you only used the business property for only half
a year. With mid-quarter convention and the property placed in service
in the first quarter, the depreciate rate is reduced as 3.5/4 (87.5%)
for the first year, and 12.5% for the last year.

If we use above method alone, then the cost basis can never be fully
deprecated, so there is an additional rule that we switch to straight line rate
[over the remaining years] when the straight line rate is equal or higher.

The following is reproduced from Table A-1 of [IRS Publication 946](https://www.irs.gov/pub/irs-pdf/p946.pdf) for MACRS
applicable percentage for property class 3-, 5-, 7-, 10-, 15-, and
20-Year Property with Half-Year Convention.

Recovery Years | 3-Year | 5-Year | 7-Year | 10-Year | 15-Year | 20-Year
---:           | ---:   | ---:   | ---:   | ---:    | ---:    | ---:
1  |     33.33  |  20.00   | 14.29  |  10.00  |   5.00   |   3.750
2  |     44.45  |  32.00   | 24.49  |  18.00  |   9.50   |   7.219
3  |   \*14.81  |  19.20   | 17.49  |  14.40  |   8.55   |   6.677
4  |      7.41  |\*11.52   | 12.49  |  11.52  |   7.70   |   6.177
5  |            |  11.52   |\*8.93  |   9.22  |   6.93   |   5.713
6  |            |   5.76   |  8.92  |   7.37  |   6.23   |   5.285
7  |            |          |  8.93  | \*6.55  | \*5.90   |   4.888
8  |            |          |  4.46  |   6.55  |   5.90   |   4.522
9  |            |          |        |   6.56  |   5.91   | \*4.462
10 |            |          |        |   6.55  |   5.90   |   4.461
11 |            |          |        |   3.28  |   5.91   |   4.462
12 |            |          |        |         |   5.90   |   4.461
13 |            |          |        |         |   5.91   |   4.462
14 |            |          |        |         |   5.90   |   4.461
15 |            |          |        |         |   5.91   |   4.462
16 |            |          |        |         |   2.95   |   4.461
17 |            |          |        |         |          |   4.462
18 |            |          |        |         |          |   4.461
19 |            |          |        |         |          |   4.462
20 |            |          |        |         |          |   4.461
21 |            |          |        |         |          |   2.231

Let us derive the formula, for half-year convention as an example.

For the first year, the percentage is 1/Y * D * 50% = D/2Y. According
to [IRS Publication 946](https://www.irs.gov/pub/irs-pdf/p946.pdf), the 3-, 5-, 7-, and 10-year classes use 200%
and the 15- and 20-year classes use 150% declining balance depreciation.
So for 20-year class property, the depreciation percentage is 1.5/(2\*20)
= 3.75% which is consistent with what in the table, similarly we can
verify all other classes in the table.

For the second year, the remaining balance is `1-D/2Y`, and the rate is:
`1/Y*D`, so the depreciation percentage is `(1-D/2Y)*D/Y`.

For the third year, the remaining balance is `(1-D/2Y)(1-D/Y)`, and the
rate is still `D/Y`, so the depreciation percentage is `(1-D/2Y)(1-D/Y)*D/Y`.

Generally, for the Nth year, the depreciation percentage is:

```
(1-D/2Y)(1-D/Y)^(N-2)*D/Y
```

Let us verify for the 5th year 15-Year class
property, we have D=1.5, Y=15, N=5, so the percentage should be:

```
(1-1.5/(2*15))*(1-1.5/15)^(5-3)*1.5/15 = 7.695%
```

and it is.

Now we need to find the year X in which we should switch to straight line
depreciation. At year X, we have `Y-(X-1)+1/2 = Y-X+3/2` years remaining,
we added 1/2 because the first year is treated as half year, so we
need another 1/2 to make up the full Y years. The straight line rate is
`1/(Y-X+3/2)` over the remaining balance, we equalize this to D/Y to find X:

```
1/(Y-X+3/2) = D/Y
```

Solving the equation we have:

```
X=Y*(1-1/D)+3/2
```

The depreciation rate is:

```
(1-D/2Y)(1-D/Y)^(N-2)*1/(Y-X+3/2)
```

for all years except the last year which is the half of the above percentage.

Let us verify for 7-Year class property, Y=7, D=200%, so
`X=7*(1-1/2)+3/2=5`, and it is. From 5th year, it is switches to straight
line depreciation, and the depreciation rate for 5th, 6th, and 7th
years is:

```
(1-2/2/7)*(1-2/7)^(5-2)/(7-5+3/2) = 8.925%
```

Please note also how the percentage alternates between 8.92 and 8.93
over the years. IRS tries to be as precise as possible beyond the second
decimal point.

To summarize, for half year convention, the depreciation percentage is:

```
P = 1-D/2Y                              for N=1
    (1-D/2Y)(1-D/Y)^(N-2)*D/Y           for N>=2 and N < ceiling(Y*(1-1/D)+3/2)
    (1-D/2Y)(1-D/Y)^(N-2)/(Y-N+3/2)     for N>= ceiling(Y*(1-1/D)+3/2) and N < Y+1
    (1-D/2Y)(1-D/Y)^(N-2)/(Y-N+3/2)/2   for N=Y+1
```
 
where `ceiling(x)` is the least integer greater than or equal to x.

From this derivation and verification we can see the tax code is not a
mess of rules, in it there is strict logic and mathematical precision.
We will see other examples. By the way, the commonwealth of Virginia does
not honor the federal accelerated depreciation, so every year we need add
a portion of the extra depreciation as compared to linear depreciation to the Virginia income in early
years, and subtract deficiency in depreciation in later years, and this appears as mysteriously as
"fixed date conformity".

PS: The equation can be extended to any convention. Let p denotes the portion
for the first year the asset is in service, for example, if an asset is placed
in service in December with Mid-Quarter convention, then d=1/8. The general
equation is:

```
P = 1-pD/Y                                  for N=1
    (1-pD/Y)(1-D/Y)^(N-2)*D/Y               for N>=2 and N < ceiling(Y*(1-1/D)+2-d)
    (1-pD/Y)(1-D/Y)^(N-2)/(Y-N+2-p)         for N>= ceiling(Y*(1-1/D)+2-d) and N < Y+1
    (1-pD/Y)(1-D/Y)^(N-2)/(Y-N+2-p)*(1-p)   for N=Y+1
```

--  
Michael Wang, [Enrolled agent](https://en.wikipedia.org/wiki/Enrolled_agent)  
Tax Professional Since 2005, All States.  
Admitted to Practice Before the IRS.  
Email: mwang@unixlabplus.com  
Wechat ID: puravidawechat  
