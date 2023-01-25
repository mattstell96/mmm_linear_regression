<h1> Understanding Marketing Mix Modeling </h1>

<p align="center">

<h2>Description</h2>

<h3>Introduction</h3>

The goal of this project is to explore and apply the basic concepts behind Marketing Mix Modeling.

MMM is a family of statistical tehcniques applied to historical data to understand the attribution and the “marginal contribution” of individual factors (facebook ads, amazon ads…) on our ROI. Typical goals in MMM are:

- Statisticall attribution of channels
- ROI Contribution of adv channels
- Forecasting sales
- Budget Allocation

💡 It is crucial to distinguish:
- **MMM (Marketing Mix Modeling)**: ignores the cookies, and tracks how efficient is the overall investment
- **MTA (Multi-Touch Attribution)**: using cookies to track the behavior of the single user

... MMM is on the rise because the importance of offline channels combined with the recent no-cookie policies stemming from the GDPR and the CCPA are making it very tough to track the user along the various media touchpoints.

<h3>MMM in Practice</h3>

In practice, an MMM project results in a regression algorithm, whereby the aim is to forecast a given KPI (i.e. sales, impressions...) using a set of predictors including data about online and offline campaigns as well as external factors such as seasonality and competitors' initiatives. The algorithm takes the form of OLS Linear Regression or Bayesian Regression; the former is more popular, but the latter is gaining ground thanks to Google's [LightWeight-MMM Python library](https://github.com/google/lightweight_mmm).

💡 This project follows the OLS Linear Regression approach; it ignores the effect of external factors (no control variables) and focuses on sales.

***-> Sales = constant + predictors effect + control variables effect***

<h3>The Nature of Ads</h3>

While it is possible to just fit a Linear Regression model to a raw dataset containing data about sales and advertising investment on different media channels for a given period, it is important to take into account 2 concepts when dealing with MMM:

1. **AdStock:** There is a decay (or “lag”) effect in advertising, whereby an ad watched today might generate a sale in 2 weeks. This lag might be anywhere from 1 to 7 weeks, and it varies according to the media type, the industry, and the specific product. 

2. **Diminishing returns:** The marginal benefit (in terms of sales, impressions, new customers...) of increasing ad investment from $1 to $100 is greater than the one that results from increasing from $500 to $599.

These two concepts cannot be ignored. In particular, in every MMM project the ad investment for a given channel should always be transformed into AdStock using one of 3 functional forms: *classic AdStock, Hill AdStock, Carryover*.

💡 In this project the AdStock transformation is the most basic one: ***AdStock(t) = AdStock(t-1) * Decay_Factor + Investment(t)***

<h3>The MMM Process</h3>

This project follows a linear and simple methodology:
1. **EDA**
2. **PreProcessing**
3. **Marketing Mix Modeling**
4. **Analysis**

💡 In a real MMM project the process would be iterative:
- The decay factor in the AdStock formula would be optimized, and not guessed
- After the analysis, the budget would be optimized (here the budget is ignored)

<h2>Code</h2>










