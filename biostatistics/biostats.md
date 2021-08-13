## Important links

### Unit 2

1. Cumulative Frequency: https://www.statisticshowto.com/probability-and-statistics/statistics-definitions/cumulative-frequency-distribution/
2. Histograms: [watch statquest](https://youtu.be/qBigTkBLU6g)
3. Distributions: Both histograms and curves are distributions. Curves show us how the probability of the measurements are distributed (Y axis represents the relative probability of a measurement). Advantages: If we don't have enough time and money and measurements, we still can have a curve that can fairly approximate how the distribution of measurements will look like. Also there might be some empty bins too without any measurement but still it gives probability of that bin too. [watch statquest](https://www.youtube.com/watch?v=oI3hZJqXJuc)
4.   The Normal Distribution: [watch statquest](https://www.youtube.com/watch?v=rzFX5NWojp0). The width of the Bell curve is ur standard deviation. ANd width in turn tell us how tall the curve will be. The wider the curver, the shorter the heigh of curve. The narrower the curve the taller.
5.   Population Parameters: [watch statquest](https://www.youtube.com/watch?v=vikkiwjQqfU)


## Distribution Curves

 - We have advantage when we have distribution curve over the histogram alone. It helps us calculate the probability of the bins that do not contain any datapoint.   
 - Also, if don't have enough time or money to get a ton of measurements, the approximate distribution curve based on mean and SD of the data is usually sufficient enough. Thus using a curve can save us lot of time and money!!  Both the histogram and curve are distributions. They show us how the probabilities of measurements are distributed.

#### Normal Distribution (ND)
They are always centered around the average values.
The width of the curve is defined by the standard deviation. Knowing SD is helpful because normal curves are frawn such that 95% of the measurements fall between +/-2 SD around the mean.
To draw a ND you need:
 1. The average measurement. This tells u where the centre of the curve goes.
 2. SD. This tells u how wide the curve should be. And the width of the curve determines how tall it is. The wider the curve, the shorter. The narrower the curve, the taller.
 The normal distribution is kind of magical in that we see it a lot in nature. The reason is "Central Limit Theorem"

The `Central Limit Theorem` shows us that no matter what distribution your measurements follow, the distribution of the `means` will always be a normal distribution (i.e. if you randomly sample few measurements and calculate the mean and plot histogram and repeat this 100 times, you will end up getting a distribution of the means and that will always be normally ditributed, no matter if the distribution of the datapoint is exponential, parabolic, uniform or blah! blah!).

So now what are the practical implications of knowing that means are normally distributed? When we do an experiment we do not always know what distributions our data comes from. To this the central Limit theorem says "Who cares". Because we know that the samples mean is normally distributed, we do not need to worry too much about the distribution that the samples come from. We can make confidence intervals using means distribution, do t-tests, where we ask if there is a difference betwee the means from two samples, and anova where we ask if there is a difference among the means from three or more samples and any statistical tests that uses the sample mean.

NOTE: It is advisable to have atleast a sample size of 30 (randomly sampling 30 values for the mean claculation) for the CLT to be true. Alos, to have CLT work at all, you have to have to be able to calculate the mean from your sample. Cauchy Distribution doesnt have a sample means but it rarel occurs in nature.

## Population Parameters
THe mean and SD of a normal curve that represent the population are called population parameters. For an exponentioal distribution, the shape of the distribution is determined by the Rate. If the distribution represent a population, it will become population rate. Similarly, in gamma distribution, the shape and rate parameters will become population shape and population rate.

The reason why we want to know the population parameters is to ensure that the results drawn from our experiment are reproducible. For example, if you have multiple replicates for GeneX and it's distribution, ideally the replicates should have datapoints that are part of previous distribution. Even though the replicates might differ from each other in terms of population parameters, we can use statsitics to quantify how different they are using a p-value or confidence interval. We will see that they might not be significantly different. This means two replicates are similar and that they are reproducible.

NOTE: More data=more confidence. One of the goal in stats is to quantify how much confidence can we have on the population parameters. Specifically, statisticians often calculate the p-values and confidence intervals to quantify the confidence in the estimated parameters.

Remeber: We rarely, if ever have population data. Therefore we rarely calculate the population parameters. We therefore use a subsample of the actual population and calculate the "estimated mean" and "estimated SD"

## Mean, Variation and SD

```math
$$\bar{X} = \frac{\sum_{i=1}^{n} x_{i}}{n}$$
```
