# Ultimate Inc. Takehome Challenge
___

## Part 1 - Exploratory Data Analysis

See ultimate_eda.ipynb
___

## Part 2 - Experiment and Metrics Design

**Metric Choice**

Since the goal of the toll-reimbursement incentive is to get drivers to drive less exclusively in a single city, a simple and effective metric for this experiment would be how far each driver's proportion of pickups in Gotham City (P<sub>G</sub>) is from the optimal value of 0.5 (perfect parity between the two cities). Formally, this would be calculated as the absolute value of the difference between 0.5 and P<sub>G</sub>. The best score for a driver would be 0, and the worst would be 0.5. The scores for all drivers would be averaged to generate a single metric for a group.

A distinct advantage of this metric is that it is simple, and therefore easy to explain to lay stakeholders. It is also linear with regard to changes in proportion, so that the metric improves as much with a change of P<sub>G</sub> from 0 to 0.1 as it does from 0.4 to 0.5.

Another possibility is the root-mean-square distance of P<sub>G</sub> from 0.5. However, since P<sub>G</sub> exists in the range from 0 to 1, the root-mean-square distance will actually vary less than the absolute distance. This somewhat negates the usual benefit of RMSE in punishing extreme values more.

A final metric to consider might be the geometric mean of the proportion of pickups in each city. In this case, the geometric mean will be the square root of P<sub>G</sub>*(1-P<sub>G</sub>). The geometric mean would heavily punish exclusivity to one city, while punishing smaller deviations from 0.5 to a much lesser extent. This metric therefore has the benefit of more readily responding to a shift of exclusive drivers to non-exclusivity, rather than a shift of drivers who are already relatively close to parity, even closer to parity. The downsides of this metric, however, are that it is more difficult for the layperson to understand, and it is unclear in this case whether extreme deviations of P<sub>G</sub> from 0.5 should be punished so much more than less-extreme deviations.

If I were faced with this project as a data scientist, I would use both absolute distance and geometric mean as metrics in my evaluation of the success of the experiment, as they capture different aspects of the driver response to the toll-reimbursement incentive. However, I would focus mainly on the absolute distance metric when explaining the results of the experiment to lay stakeholders.

**Experiment Design**

