# GDP_R_Modelling

From mathematics to coding models

This program finds the expected value of life satisfaction based on the inputted value of country's GDP. The Life satisfaction is within the range 0 to 10, 10 being the highest. Make sure to change the address of filename depending upon where you store it in your computer.


## Structure  of the Model

|             |   |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                     |   |
| ----------- | - | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | - |
| model       |   | a list specifying an ARIMA model. The components**ar** and **ma**, if present, should be numeric vectors giving the autoregression and moving average parameters for the model. If you also want a difference parameter, supply the **order** component, a three-long integer vector giving the length of the **ar** component, the number of differences, and the length of the **ma** component, respecively. (If supplied, the first and last elements of **order** must match the lengths of the **ar** and **ma** components.) |   |
| n           |   | the length of the series to be simulated.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                           |   |
| innov       |   | a univariate time series or vector of innovations to produce the series. If not provided,**innov** is generated using **rand.gen**. Missing values (**NA**s) are not allowed. If provided, its length must match the **n** argument.                                                                                                                                                                                                                                                                                                                        |   |
| n.start     |   | the number of start-up innovations. The start-up innovations are generated by**rand.gen** if **start.innov** is not provided. **n.start** must be as long as **ar + ma**.                                                                                                                                                                                                                                                                                                                                                                                   |   |
| start.innov |   | a univariate time series or vector of innovations to be used as start up values. Missing values (**NA**s) are not allowed. These are transformed by the Choleski "square root" of the correlation matrix corresponding to the model so the simulated process begins with something close to its stationary state if you supply iid (independent and identically distributed) innovations.                                                                                                                                                                                     |   |
| rand.gen    |   | a function that is called to generate the innovations. Usually,**rand.gen** is a random number generator.                                                                                                                                                                                                                                                                                                                                                                                                                                                                     |   |


### BACKGROUND

The Gross Domestic Product (GDP) is that the value of all product and
services made at intervals the borders of a nation in an exceedingly year. In this
paper, the Box-Jenkins approach has been used to build the appropriate
Autoregressive-Integrated Moving-Average (ARIMA) model for the Egyptian
GDP data. Egypt’s annual GDP data obtained from the World-Bank for the years
1965 to 2016. We find that the appropriate statistical model for Egyptian GDP is
ARIMA (1, 2, 1). Finally, we used the fitted ARIMA model to forecast the GDP
of Egypt for the next ten years.
Keywords: Box-Jenkins approach, Egypt, Forecasting, Goodness-of-fit
measures, Gross domestic product, Residuals analysis.

#### DEFINITION


GDP represents the market value of all goods and services produced by the
economy during the period measured, including personal consumption,
government purchases, private inventories, paid-in construction costs and
the foreign trade balance (exports minus imports). GDP can be measured in three
ways: (i) the expenditure approach, (ii) the production approach, and (iii) the
income approach.
The issue of GDP has becomes the most concerned amongst macro economy
variables and data on GDP is regarded as the important index for assessing the
national economic development and for judging the operating status of macro
economy as a whole (Ning et al, 2010). It is often considered the best measure of
how well the economy is performing. Also, it is a vital basis for government to set
up economic developmental strategies and policies.

### MATHEMATICAL FRAMEWORK


The time series analysis can provide short-run forecast for sufficiently large
amount of data on the concerned variables very precisely, see Granger and
Newbold (1986). In univariate time series analysis, the ARIMA models are
flexible and widely used. The ARIMA model is the combination of three
processes: (i) Autoregressive (AR) process, (ii) Differencing process, and (iii)
Moving-Average (MA) process. These processes are known in statistical literature
as main univariate time series models, and are commonly used in many
applications.
2.1. Autoregressive (AR) model
An autoregressive model of order p, AR (p), can be expressed as:
𝑋𝑡 = 𝑐 + 𝛼1𝑋𝑡−1 + 𝛼2𝑋𝑡−2 + ⋯ + 𝛼𝑝𝑋𝑡−𝑝 + 𝜀𝑡
; 𝑡 = 1,2, … 𝑇, (1)
where 𝜀𝑡
is the error term in the equation; where 𝜀𝑡 a white noise process, a
sequence of independently and identically distributed (iid) random variables with
𝐸(𝜀𝑡
) = 0 and 𝑣𝑎𝑟(𝜀𝑡
) = 𝜎
2
; i.e. 𝜀𝑡 ~𝑖𝑖𝑑 𝑁(0, 𝜎
2
). In this model, all previous
values can have additive effects on this level 𝑋𝑡 and so on; so it's a long-term
memory model.
2.2. Moving-average (MA) model
A time series {𝑋𝑡
} is said to be a moving-average process of order q, MA (q),
if:
𝑋𝑡 = 𝜀𝑡 − 𝜃1𝜀𝑡−1 − 𝜃2𝜀𝑡−2 − ⋯ − 𝜃𝑞𝜀𝑡−𝑞.
