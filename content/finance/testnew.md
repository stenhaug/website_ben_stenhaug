---
title: Testnew
author: 'Ben Stenhaug'
date: '2021-07-11'
slug: test_new
categories: []
tags: []
comments: yes
showcomments: yes
showpagemeta: yes
---

WherethisIn [**saving for retirement**](https://www.benstenhaug.com/finance/investing_for_retirement/), we talked about a generic retirement account, but there are actually two types.

With a Roth retirement account, you invest money that you already paid income taxes on. This is how just about all money works: You earn income, pay income taxes, and then get to use the remainder for investing or consuming. 
.
With a Traditional retirement account, you don’t pay income taxes until retirement (sometimes called tax-deferred accounts — you’re deferring paying taxes until retirement). This could be a good option if you’ll pay a lower tax rate when you retire.

To make this clear, imagine you make $1000 in pre-tax income that you want to save for retirement, your income tax rate right now is 30%, your income tax rate when you retire will be 20%, and your investments will be multiplied by ten between now and retirement.

If you use a Roth retirement account, you pay $1000 * 30% = $300 in taxes right now. You then have $1000 - $300 = $700 to invest in the Roth retirement account. This money grows to $700 * 10 = $7,000, which you can withdraw tax-free when you retire.

If you use a Traditional retirement account, you don’t pay any taxes right now. You invest all $1000 in the Traditional retirement account. This money grows to $1000 * 10 = $10,000. You have to pay 20% income tax on this entire amount^[A common misconception is that the Roth retirement account is better because you’re paying tax before your investment grows. The incorrect logic is that it’s better to pay taxes on $1,000 before the investment grows than on $10,000 after the investment grows by a factor of 10. In fact, it doesn’t matter — imagine the tax rate is 30% now and 30% in retirement: Roth retirement account end value = Traditional retirement account end value $1,000 x 30% x 10 = $1,000 x 10 x 30%. Taxes multiply by a percentage, and order doesn’t matter in multiplication (the fancy name is the [commutative property of multiplication](http://www.mathematicsdictionary.com/english/vmd/full/c/vepropertyofmultiplication.htm)). This misconception is explained by [the Bogleheads wiki](https://www.bogleheads.org/wiki/Traditional_versus_Roth#Common_misconceptions) as that it doesn’t matter if the investment is taxed at the seed (Roth retirement account) or at harvest (Traditional retirement account).] which is $10,000 * 20% = $2,000. You end up with $10,000 - $2,000 = $8,000.

### Should you use a Roth or a Traditional retirement account?

Just about everyone using retirement accounts has to choose between Roth and Traditional. As such, there is a lot of contradictory and often bad advice out there.

The key complicating factor is that retirement accounts have limits on how much you can contribute. To make things more confusing, the limit is after-tax for Roth retirement accounts but pre-tax for Traditional retirement accounts. Because pre-tax money has less value (you still have to pay taxes on it!), the limit for Traditional retirement accounts is effectively less.

If you aren’t going to hit the contribution limit, then choosing between a Roth and Traditional retirement account boils down to simply comparing your income tax rate now to your income tax rate in retirement:

- If your income tax rate now is lower than your income tax rate in retirement, then pay taxes now by investing in a Roth retirement account.

- If your income tax rate now is equal to your income tax rate in retirement, then it doesn’t matter^[But still choose Roth because having income from Traditional can have other tax consequences like getting social security payments taxed which are aren't accounting for here.].

- If your income tax rate now is greater than your income tax rate in retirement, then pay taxes later by investing in a Traditional retirement account.

Of course, it’s impossible to know for sure what your tax rate will be in retirement — and in practice it’s even confusing to figure out what your tax rate is now — so even though the rule is clear, it’s still hard to implement.

To further complicate the matter, if you are going to hit the contribution limit, then choosing between a Roth and Traditional retirement account becomes more complex. Imagine that the contribution limit is $6,000, your income tax rate is 30% now, and your income tax rate in retirement is 20%.

- Roth - To meet the $6,000 limit, you need to invest $6,000 / (100% - 30%) = $8,570 in pre-tax income.

- Traditional - To have an apples-to-apples comparison, we need to think through what you could do with $8,570 in pre-tax income. You can first contribute $6,000 to the Traditional retirement account. You then have $8,570 - $6,000 = $2,570 in pre-tax income. After taxes, that turns into $2,570 x (100% - 30%) = $1,800 which you can invest in a taxable account.

Now we need to compare these two cases. In both, you started with $8,570.

**Roth**

- $6,000 in a retirement account that you don’t owe taxes on

- $6,000 in after-tax retirement

- $0 in a taxable account

**Traditional**

- $6,000 that you’ll have to pay taxes on when you withdraw. The tax rate at retirement is 20%, so this is like $4,800. With the leftovers, you invested $1,800 in a taxable account.

- $4,800 in after-tax retirement

- $1,800 in a taxable account

This boils down to the Roth has $1,200 more in after-tax retirement, and the Traditional has $1,800 more in a taxable account.

Which is better? $1,800 is more than $1,200, but money in a retirement account is worth more.

This is precisely the Retirement Multiplier! If the retirement multiplier is at least $1,800 / $1,200 = 1.5, then it’s better to invest in a Roth retirement account. If not, then a Traditional retirement account is better.

There is a general result in this example. The 1.5 that we got from $1,800 / $1,200 is also the ratio of the tax rate now of 30% / 20%.

This leads to to the general Roth vs. Traditional comparison equation:

$$
\dfrac{\text{Income tax rate now}}{\text{Income tax rate in retirement}} \text{vs. Retirement Multiplier} 
$$

In essence, this compares a Traditional retirement account’s benefit of deferring taxes to when you pay a lower income tax rate vs. a Roth retirement account’s advantage of contributing more to a retirement account.

- If the left-hand side (the ratio of income tax rates) is greater, contribute to a Traditional retirement account.

- If the right-hand side (the retirement multiplier) is greater, contribute to a Roth retirement account.

### The Bottom Line

1. Retirement accounts are better than taxable accounts because you don’t pay capital gains tax or taxes on dividends
1. 38% of Americans don’t have a retirement account, and it’s worse for younger, lower-income, and minority individuals.
1. We can get a sense of how important it is to save for retirement by understanding
    1. Investment Multiplier: How much more purchasing power will you have if you invest in a taxable account.
    1. Retirement Multiplier: How much more purchasing power will you have if you invest in a retirement account. (I'm working on a Retirement Multiplier calculator)
1. A Roth retirement account has you pay income taxes now. A Traditional retirement account has you pay income taxes when you retire. Choosing between them is complicated:
    1. If you won’t hit your contribution limit, then use a Roth retirement account if your tax rate now is less than or equal to your tax rate when you retire.
    1. If you will hit your contribution limit (which you should try to do!), then use a Roth retirement account if your Retirement Multiplier is greater than or equal to the ratio of your income tax rate now to your income tax rate when you retire.
