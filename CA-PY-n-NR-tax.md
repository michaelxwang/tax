How does California compute its tax for part year resident and nonresident?

If you are a part year resident or nonresident of California, you maybe surprised to find out how California computes its tax: First it figure the tax based on total income from all states, and then apply the ratio of California income over the total income.

For example suppose you made $10,000 in California, and then moved to Washington and make another $10,000 there. California will add both the income, compute tax based on $20,000 and then divide the tax amount by 2, and this is the tax you need to pay California.

Why should California compute its tax this complicated way instead just using its own income? The answer is that the tax is higher this way due to the graduated tax rates. Let us use a simple mathematical model to illustrate the differences. Suppose the tax rate is 10% for the first $10,000 and 15% for the second $10,000. To use only CA income to compute tax, the result is $1,000. To use the California method, the result is:

```
tax_of(10,000 + 10,000) * 10,000/(10,000 + 10,000)
= (10,000 * 10% + 10,000 * 15%) * 50%
= 2,500 * 50%
= 1,250
```

Please note California tax increases if you made more money outside of the state. Not only California uses income from other states, but also adds back certain deductions permitted by Federal tax code, for exampe, the pre tax contributions to Health Savings Account, and the $5,000 exemption allowed by US-China tax treaty, and they become global income *per California low*, and California income as well if the deduction takes place in California.

In general, suppose A is California income, and B is income out side of California, the formula used by California to compute tax is:

```
CA tax = tax_of(A+B) * A/(A+B)
```

We have just illustrated that:

```
tax_of(A+B) * A/(A+B) > tax_of(A)
```

I believe it can be mathematically proven that it is generally true when `tax_of()` is an increasing function.

You may ask: what can I do about this? Well if you are single, you cannot do anything. However if you are married, and one spouse is a nonresident, you can choose to file federal jointly, and California separately because the [California law](https://www.ftb.ca.gov/individuals/filing-status-information.shtml) states:

>Use the same filing status for California that you used for your federal income tax return ...
 
>Exception: If you file a joint tax return for federal purposes, you may file separately for California if either spouse was:

>An active member of the United States armed forces or any auxiliary military branch during 2017.

>A nonresident for the entire year and had no income from California sources during 2017.

Suppose the spouse A is MD resident and the spouse B is CA resident, and you do not want to A's income to inflate CA tax, you need to file a joint return for federal, and perhaps a joint return for MD, but a separate return for CA.

Most likely you cannot do this with a single return, you need to create separate return for spouse B but only file for state only, in which federal return is an "as if" return used for state only but will not actually be filed.

If your software does not allow you to create two returns with the same primary social security number, you need to switch the positions of the spouses in the joint return to make it work.

```
Michael Wang, Enrolled Agent.
Admitted to Practice Before the IRS.
Tax Professional Since 2005, All States.
mwang@unixlabplus.com
```
