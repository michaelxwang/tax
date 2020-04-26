### Repayment: deduction, credit, and state

Repayment is paying back the money you have previous received and
have paid the tax. For example, you need to pay back the tuition
reimbursement, signing bonus if you leave the company before serving
the number of years as required. Another example is to pay back
the salary during your temporary disablement when the income was
paid later by the insurance company.

Since you have paid the tax on the income at the time when you
believe you had the right to claim to the payment, you should be
able to recover the tax paid when the income was repaid. You can
either claim deduction _or_ credit (if the repayment is more than
$3,000) _in the year of the repayment_ according to [IRS publication
17](https://www.irs.gov/pub/irs-pdf/p17.pdf).

For W2 repayment, the deduction should be claimed in [Schedule
A](https://www.irs.gov/pub/irs-pdf/f1040sa.pdf) (Itemized Deduction).
For repayment of $3,000 or less, enter it in line 23 subject to a
threshold of 2% of your adjusted gross income.  For repayment over
$3,000, enter it in line 28 _not_ subject to a threshold.

If the repayment is more than $3,000, you can take a credit. The
amount of credit is the additional tax you paid _in prior year when
you included the income which you repaid in a later year_. You enter
the credit amount in line 73 of [form
1040](https://www.irs.gov/pub/irs-pdf/f1040.pdf), check the box d,
and write "st \<N\>" in the space. The statement \<N\> should include
"IRC 1341" and the amount of credit.

The state treatment needs to be handle state by state.
[California](https://www.ftb.ca.gov/forms/2017/17_540bk.pdf) mirror
the federal treatment, and you can claim either reduction or credit
(if repayment is more than $3,000) independent of the federal
selection.  As the logic is more complex for natural language, I
wrote a section of pseudo code:

```
IF ( repayment > $3,000 AND CA => "CREDIT" ) {

   IF ( US => "DEDUCTION ) {

      Enter the amount of the federal deduction as a negative amount
      on Schedule CA (540), line 41 ("Other adjustments including
      California lottery losses") to negate the federal deduction
      IF it is carried over to CA.
   }

   Add the credit amount on line 76, the total payment line, of the
   Form 540. To the left of the total, write "IRC 1341" and the
   amount of the credit.
} 
ELSE IF ( CA => "DEDUCTION" ) { /* For any amount of repayment */
   IF ( US => "CREDIT" ) {

      Enter the amount of deduction as a positive number on On CA (540)
      line 41 "Other adjustments including California lottery losses".
      Deductions of $3,000 or less are subject to the 2% federal AGI
      limit.
   }
   ELSE IF ( US => "DEDUCTION" ) {

      Null /* There is nothing to do as the deduction has been carried over */
   }
}
```

VA deduction follows the federal, and credit is also allowed per
[this](https://tax.virginia.gov/laws-rules-decisions/rulings-tax-commissioner/87-190)
letter ruling.

Generally speaking it is better to claim deduction if the current year's income is higher and to
claim credit when prior year's income is higher. However, you must use itemized deduction to deduct
the repayment which may limit your deduction. The ultimate test is to do two returns and compare
the result, and do the same for the state as well.

[The Tax Cut and Jobs Act](https://en.wikipedia.org/wiki/Tax_Cuts_and_Jobs_Act_of_2017)
eliminated the miscellaneous itemized deduction subject to threshold of 2% of the adjusted global income,
it remains to be seen how the deduction for the repayment of $3,000 or less.

```
Michael Wang, EA
Tax Return Over Cloud
Tax Professional Since 2005, All States.
Admitted to Practice Before the IRS.
mwang@unixlabplus.com
Wechat ID: puravidawechat
```
