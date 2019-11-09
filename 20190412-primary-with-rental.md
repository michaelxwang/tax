### Tax on the sale of primary residence with rental history

This article discusses what taxes to be paid when you sells primary home
with rental history. The prerequisite for this article is the taxation
on the sale of rental home discussed in the
[other article](https://github.com/michaelxwang/tax/blob/master/sale-of-rental-home.md).

It is easier to explain the tax theory with an example, so here it is:

>Jack Ma bought a rental house in 2010 for $200,000. After living there
>as primary residence for a year, he rented for three years (2011, 2012,
>2013) and depreciated 20,000 during the rental period. Afterwards, he
>lived there for two more years (2014, 2015) and then sold the house for
>250,000. How should Jack pay tax on the sale? (Assuming the land value
>is zero or did not change).

Let us review the tax theory involved in solving this problem:

- General rule [IRC 121(a)](https://www.law.cornell.edu/uscode/text/26/121): "Gross income shall not include gain
from the sale or exchange of property if, during the 5-year period
ending on the date of the sale or exchange, such property has been
owned and used by the taxpayer as the taxpayer’s principal residence
for periods aggregating 2 years or more." Taxpayers who satisfy this
so called "2 out of 5 rule" can exclude up to 250K (single) or 500K (married).

- Limitation rule [IRC 121(b)(5)(A)](https://www.law.cornell.edu/uscode/text/26/121): "Subsection (a) shall not apply
to so much of the gain from the sale or exchange of property as is
allocated to periods of nonqualified use." The exclusion of gain is limited
to the period of primary residence (prorate by time).

Now we can start the solution.

First we shall calculate the cost basis. Because depreciation reduced
the cost basis, the cost basis at the time of sale is:

```200,000 - 20,000 = 180,000```

The gross income is the sale price less the cost basis (ignore the
selling expenses), which is:

```250,000 - 180,000 = 70,000```

Among the 70,000 gain, 20,000 is attributed to depreciation, which is
unrecaptured 1250 gain. This part should be treated separately later,
for now, let us deal with the remaining 50,000 gain.

During the 6 year ownership, Jack Ma used as primary resident for 3
years, and rented for 3 years, the gain corresponding to the period
of primary resident is 25,000 which will be excluded by IRC section
121. The remaining 25,000 is IRC section 131 gain, and treated as long
term capital gain.

It does not matter in what period the value of the house increased,
it is prorated linearly according to the period of the rental property
and primary residence.

Since the new law was passed in 2009 and is
not retrospective, the rental period before 2009 is treated as primary
residence period. The [IRC 121(b)(5)(C)(i)](https://www.law.cornell.edu/uscode/text/26/121) says:

>The term “period of nonqualified use” means any period (other than
>the portion of any period preceding January 1, 2009) during which
>the property is not used as the principal residence of the taxpayer
>or the taxpayer’s spouse or former spouse.

Another common exception is that the last rental period counts as primary residence,
[IRC 121(b)(5)(C)(ii)(I)](https://www.law.cornell.edu/uscode/text/26/121)
says:

>any portion
>of the 5-year period described in subsection (a) which is after the
>last date that such property is used as the principal residence of
>the taxpayer or the taxpayer’s spouse". The last rental period does not
>count.

We do not have these situations in this example, but they are important to note.

Now let us go back to the 20,000 unrecaptured 1250 gain. It is said
"on the net" that the gain is taxed by the 25% fixed rate, this is not
accurate. The correct statement is this part of gain is taxed up to 25%
depending on the tax bracket of Jack Ma.

Suppose Jack's income is low, which equals the deduction and exemption,
so his taxable income consists of this 20,000 unrecaptured 1250 gain,
plus the 25,000 long term capital gain not excluded by IRC section 121,
totaling 45,000.

Suppose filing status of Jack Ma is head of household, since the
income is below the starting point of 25% tax rate \$50,401 (2016),
so his long term capital gain is 0%. We know with certainty that any
number multiplied by zero is zero, so the long term capital gain tax is
zero. That is, although Jack has a capital gain which is not excluded
by the IRC section 121, the tax is eliminated by the 0% tax rate.

According the illustration of the chart in prerequisite article, since it
is below the 25% threshold, the 20,000 unrecaptured 1250 gain is taxed
with the ordinary tax rate, which is 15% for part of the income and 10%
for part of the income. This is way below the fixed 25%.

Now let us look at another extreme. Suppose Jack Ma is super rich that
his other income exceeded the 39.6% (2016) starting point, his tax in
this situation is:

```
25,000 * 20% (capital gain) + 
20,000 * 25% (unrecaptured 1250 gain) + 
tax on other income taxed per tax table
```

Let us now enter the middle ground. Suppose the Jack's other income is
\$10,000 below the starting point of the 25% bracket $50,401 (2016), but
adding the 20,000 unrecaptured 1250 gain it will be over the threshold. In
this situation, the tax is computed according to the tax table that part
of the unrecaptured 1250 gain pays 15% tax, and the other part pays 25%,
and the overall tax rate is below 25%.

By the way, if Jack sold the house at a loss, then the loss is not
deductible because the house was a primary resident at the time of sale,
and therefore the loss is a personal loss. At the same time, there will
be no unrecaptured 1250 gain due to depreciation, i.e. there is no pay back
for the tax benefit of the depreciation taken at the rental period.

```
Michael Wang, Enrolled Agent.
Admitted to practice before IRS.
Tax professional since 2005, All states.
Email: mwang@unixlabplus.com
WeChat: puravidawechat
```
