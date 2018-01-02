## What is AMT?

AMT stands for _Alternative Minimum Tax_. According to the official definition in [26 U.S. code §55](https://www.law.cornell.edu/uscode/text/26/55) and the actual usage on [line 45 of form 1040](https://www.irs.gov/pub/irs-pdf/f1040.pdf), it is the amount by which the _Tentative Minimum Tax (TMT)_ exceeds the _Regular Income Tax (RIT)_.

The Tentative Minimum Tax (TMT) is the tax computed with a parallel method different from the regular tax compupter, which we will discuss in next section.

The relationship among Regular Income Tax (RIT), Tentative Minimum Tax (TMT), and Alternative Minimum Tax (AMT) are shown in the picture below:

<img src="https://docs.google.com/drawings/d/e/2PACX-1vQI9kDhb2-G4VDdnS19MIwtLJIJBU02ygeFdW9YxiXfOL5PM-f_9Gec-YjF96__eG3Vm-CCfKU9L5us/pub?w=391&amp;h=294">

When Tenative Minimum Tax (TMT) is greater than the Regular Income Tax (RIT), then we say you have hit the AMT, or you pay this _additional_ tax on top of the regular tax as formulated on form 1040. In reality, however, it is not that you pay another tax called AMT tax, but you just pay Tentative Minimum Tax (TMT), because AMT can be expressed as:

```
AMT = TMT - RIT
```

So the total tax you pay is:

```
Total Tax = RIT + AMT = RIT + (TMT - RIT) = TMT
```

In other words, you pay regular tax or tentative minimum tax, whichever is higher. You cannot beat IRS.

### How is Tentative Minimum Tax (TMT) computed? 

It is computed by the following steps:

- Derive the _alternative minimum tax income (AMTI)_ which is different than computing taxable income. For example, it is not allowed personal exemptions, standard deductions, and state taxes, property taxes, and job related expenses in itemized deductions.

- Subtract the _exemption_ amount for AMT purpose from the AMTI. The exemption is $83,800 (Y2016) for joint return if AMTI is less than the _phase out threshold_, which is $159,700 (Y2016). The exemption amount starts to phase out when AMTI exceeds this number by an amount equal to 25 percent of the excess. 

- Compute the tax at 26% for the portion of the income below $186,300 (Y2016), and at 28% above.

### Example

A joint filer with AGI $150,000. Suppose all their deductions are unallowed for AMT purpose. The Tentative Minimum Tax (TMT) is computed as (Y2016):

```
TMT = (150,000 - 83,800) * 26% = 17,212
```

Suppose the deduction is D, and since the personal exemptions are 8100 for 2 persons, the Regular Income Tax (RIT) is (Y2016):

```
RIT = (150,000 - D - 8100) * 25% - 8457.50
```

Obviously the more the deduction, the less regular tax. When deduction reaches 39,222, the regular tax is below the tentative miminum tax, so the AMT kicks in. 

### New tax law change

The [new tax law](https://www.congress.gov/bill/115th-congress/house-bill/1/text) did not eliminate the AMT as it should have, but increased the exemption amounts and phaseout thresholds which are tabulated below:

| Year | MFJ/QW | MFS | Single/HH |
| ---: | ---: | ---: | ---: |
| 2016 exemption | $83,800 | $41,900 | $53,900 |
| 2017 exemption | $84,500 | $42,250 | $54,300 |
| 2018+ exemption | $109,400 | $54,700 | $70,300 |
| 2016 phaseout | $159,700 | $79,850 | $119,700 |
| 2017 phaseout | $160,900 | $80,450 | $120,700 |
| 2018+ phaseout | $1,000,000 | $500,000 | $500,000 |

Also see [here](http://docs.house.gov/billsthisweek/20171218/CRPT-115HRPT-466.pdf) for more readable text.

### Conclusion

The purpose of AMT is ensure that rich people to pay a minimum amount of taxes by disallow certain deductions. However it is not so much about richness as theoretically anyone who has income greater than the AMT exemption amount can trigger AMT, rather it is about how much you have deducted unallowed amount for AMT purpose, and how much tax you have paid relative to your income. Let us use two examples to illustrate this.

Bill and Hillary Clinton did not pay AMT in their [2015 tax return](http://www.taxhistory.org/thp/presreturns.nsf/Returns/FCA79776EFA029088525800D005A016C/$file/HR_Clinton_2015.pdf) even their income is _10.5 millions_. This is because the deduction is moderate relatively speaking (and a major part of the deductions was charitable donations which were allowed), and they paid _3.2 millions_ in regular taxes. The effective tax rate is _30.5%_ which exceeds the maximum 28% AMT tax rate.

In [Donald Trump's 2005 tax return](http://www.taxhistory.org/thp/presreturns.nsf/Returns/6ECD0CC206C03A7F852580E90049B2B1/$file/trump2005tax.pdf), he paid _38 millions_ federal tax, of which _31 millions_ were attributed to AMT, without which he would have paid a little over 10% income tax of his AGI.

```
Michael Wang, EA. Admitted to Practice Before the IRS.
Tax Professional Since 2005, All States. Cloud Tax Return.
mwang@unixlabplus.com.
```
