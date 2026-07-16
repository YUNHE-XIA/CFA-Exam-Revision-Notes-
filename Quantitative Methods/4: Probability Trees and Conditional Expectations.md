# Probability Trees and Conditional Expectations | 概率树与条件期望

## 1. 核心记忆

This module focuses on probability tools used in investment decisions under uncertainty.

本章主要学习：

- expected value：期望值；
- variance：方差；
- standard deviation：标准差；
- probability tree：概率树；
- conditional probability：条件概率；
- conditional expected value：条件期望；
- Bayes' formula：贝叶斯公式。

投资分析中，未来的经济、公司盈利、债券违约、股价表现都存在不确定性，因此需要用 probability tools 来分析不同情景下的结果。

记忆：

> Expected value measures the probability-weighted average outcome.  
> Variance and standard deviation measure risk around expected value.  
> Probability trees organize scenarios and outcomes.  
> Bayes' formula updates probability when new information arrives.

---

## 2. Expected Value | 期望值

Expected value is the probability-weighted average of possible outcomes.

期望值不是历史平均数，而是对未来结果的概率加权预测。

$$
\begin{aligned}
E(X)
&=
\sum_{i=1}^{n} P(X_i)X_i
\end{aligned}
$$

其中：

- \(X_i\) = possible outcome；
- \(P(X_i)\) = probability of that outcome；
- \(E(X)\) = expected value。

投资含义：

> Expected value is the forecasted average outcome.

例如：

如果一只股票有两个可能收益：

- 60% probability of 10% return；
- 40% probability of -5% return；

则：

$$

E(R)
&=
0.60(10\%) + 0.40(-5\%) \\
&=
4\%

$$

记忆：

> Expected value = outcome × probability, then add them together.

---

## 3. Expected Value vs Sample Mean | 期望值 vs 样本平均数

Expected value and sample mean are different.

| Concept | 中文 | Meaning |
|---|---|---|
| Expected value | 期望值 | Forward-looking forecast |
| Sample mean | 样本平均数 | Historical average |

Expected value:

- based on probability；
- looks to the future；
- used for forecasting。

Sample mean:

- based on historical observations；
- each observation is equally weighted；
- describes past data。

记忆：

> Expected value = forecast.  
> Sample mean = historical average.

---

## 4. Variance | 方差

Variance measures the dispersion of outcomes around expected value.

$$
\begin{aligned}
\sigma^2(X)
&=
E\left[(X - E(X))^2\right]
\end{aligned}
$$

For a discrete random variable:

$$
\begin{aligned}
\sigma^2(X)
&=
\sum_{i=1}^{n} P(X_i)\left[X_i - E(X)\right]^2
\end{aligned}
$$

含义：

- variance measures risk；
- larger variance means greater uncertainty；
- variance is always greater than or equal to zero；
- variance is in squared units。

记忆：

> Variance measures how far outcomes are from expected value.

---

## 5. Standard Deviation | 标准差

Standard deviation is the positive square root of variance.

$$
\begin{aligned}
\sigma(X)
&=
\sqrt{\sigma^2(X)}
\end{aligned}
$$

Standard deviation is easier to interpret than variance because it is in the same unit as the variable.

例如：

- if return is measured in percentage；
- standard deviation is also measured in percentage；
- variance is measured in percentage squared。

投资含义：

> Standard deviation measures the risk or uncertainty of expected return.

记忆：

> Variance is squared risk.  
> Standard deviation is risk in the original unit.

---

## 6. Steps to Calculate Expected Value and Variance | 计算步骤

### Step 1: Calculate Expected Value

$$
\begin{aligned}
E(X)
&=
\sum P(X_i)X_i
\end{aligned}
$$

### Step 2: Calculate Deviation from Expected Value

$$
\begin{aligned}
X_i - E(X)
\end{aligned}
$$

### Step 3: Square Each Deviation

$$
\begin{aligned}
\left[X_i - E(X)\right]^2
\end{aligned}
$$

### Step 4: Weight by Probability

$$
\begin{aligned}
P(X_i)\left[X_i - E(X)\right]^2
\end{aligned}
$$

### Step 5: Add All Weighted Squared Deviations

$$
\begin{aligned}
\sigma^2(X)
&=
\sum P(X_i)\left[X_i - E(X)\right]^2
\end{aligned}
$$

### Step 6: Take Square Root

$$
\begin{aligned}
\sigma(X)
&=
\sqrt{\sigma^2(X)}
\end{aligned}
$$

记忆：

> Expected value first.  
> Then variance.  
> Then standard deviation.

---

## 7. Probability Tree | 概率树

A probability tree is a diagram that shows scenarios and possible outcomes.

概率树用于展示：

- first-stage scenario；
- second-stage outcome；
- conditional probabilities；
- final possible results。

Each branch shows a probability.

Each final path probability is calculated by multiplying probabilities along the path.

$$
\begin{aligned}
P(\text{Scenario and Outcome})
&=
P(\text{Scenario}) \times P(\text{Outcome} \mid \text{Scenario})
\end{aligned}
$$

记忆：

> Along one path: multiply probabilities.  
> Across different paths: add probabilities.

---

## 8. Conditional Probability | 条件概率

Conditional probability is the probability of one event given that another event has occurred.

$$
\begin{aligned}
P(A \mid B)
&=
\frac{P(A \cap B)}{P(B)}
\end{aligned}
$$

where:

$$
\begin{aligned}
P(B) \neq 0
\end{aligned}
$$

含义：

> P(A | B) means the probability of A given B.

例如：

- \(P(Default \mid Recession)\)：given recession, probability of default；
- \(P(High EPS \mid Declining Interest Rates)\)：given declining rates, probability of high EPS。

记忆：

> Conditional probability changes the probability after new information is known.

---

## 9. Mutually Exclusive and Exhaustive Scenarios | 互斥且完整的情景

Probability trees usually require scenarios to be mutually exclusive and exhaustive.

### Mutually Exclusive

Mutually exclusive means scenarios cannot happen at the same time.

例如：

- declining interest rates；
- stable interest rates；
- rising interest rates。

同一时期利率环境不能同时属于多个情景。

### Exhaustive

Exhaustive means the scenarios cover all possible cases.

All scenario probabilities should add up to 1.

$$
\begin{aligned}
P(S_1) + P(S_2) + \cdots + P(S_n)
&=
1
\end{aligned}
$$

记忆：

> Mutually exclusive = no overlap.  
> Exhaustive = nothing missing.

---

## 10. Total Probability Rule | 全概率公式

If \(S_1, S_2, \ldots, S_n\) are mutually exclusive and exhaustive scenarios, then:

$$
\begin{aligned}
P(A)
&=
P(A \mid S_1)P(S_1)
+
P(A \mid S_2)P(S_2)
+
\cdots
+
P(A \mid S_n)P(S_n)
\end{aligned}
$$

Compact form:

$$
\begin{aligned}
P(A)
&=
\sum_{i=1}^{n} P(A \mid S_i)P(S_i)
\end{aligned}
$$

含义：

> The unconditional probability of A is the weighted average of conditional probabilities across all scenarios.

记忆：

> Total probability = scenario probability × conditional probability, then add.

---

## 11. Conditional Expected Value | 条件期望

Conditional expected value is the expected value of a random variable given a scenario.

$$
\begin{aligned}
E(X \mid S)
&=
P(X_1 \mid S)X_1
+
P(X_2 \mid S)X_2
+
\cdots
+
P(X_n \mid S)X_n
\end{aligned}
$$

Compact form:

$$
\begin{aligned}
E(X \mid S)
&=
\sum_{i=1}^{n} P(X_i \mid S)X_i
\end{aligned}
$$

含义：

> Conditional expected value updates the forecast after a scenario is known.

例如：

- expected EPS given declining interest rates；
- expected recovery value given recession；
- expected bond return given no default。

记忆：

> Conditional expected value is expected value under one specific scenario.

---

## 12. Total Probability Rule for Expected Value | 期望值的全概率公式

The unconditional expected value can be calculated from conditional expected values.

For two scenarios:

$$
\begin{aligned}
E(X)
&=
E(X \mid S)P(S)
+
E(X \mid S^C)P(S^C)
\end{aligned}
$$

For many scenarios:

$$
\begin{aligned}
E(X)
&=
E(X \mid S_1)P(S_1)
+
E(X \mid S_2)P(S_2)
+
\cdots
+
E(X \mid S_n)P(S_n)
\end{aligned}
$$

Compact form:

$$
\begin{aligned}
E(X)
&=
\sum_{i=1}^{n} E(X \mid S_i)P(S_i)
\end{aligned}
$$

含义：

> Overall expected value is the weighted average of scenario-specific expected values.

记忆：

> Expected value today = conditional expectation under each scenario × scenario probability.

---

## 13. Conditional Variance | 条件方差

Conditional variance measures the risk of a variable under a specific scenario.

$$
\begin{aligned}
\sigma^2(X \mid S)
&=
\sum_{i=1}^{n}
P(X_i \mid S)
\left[
X_i - E(X \mid S)
\right]^2
\end{aligned}
$$

Conditional standard deviation:

$$
\begin{aligned}
\sigma(X \mid S)
&=
\sqrt{\sigma^2(X \mid S)}
\end{aligned}
$$

投资含义：

> Conditional variance helps assess risk under a particular scenario.

例如：

- EPS risk given declining interest rates；
- recovery value risk given recession；
- portfolio return risk given high inflation。

记忆：

> Conditional expected value measures scenario return.  
> Conditional variance measures scenario risk.

---

## 14. Probability Tree Calculation Logic | 概率树计算逻辑

When solving a probability tree problem:

1. Identify first-stage scenarios.
2. Assign probability to each scenario.
3. Identify outcomes under each scenario.
4. Assign conditional probability to each outcome.
5. Multiply along each path.
6. Add terminal probabilities if needed.
7. Calculate expected value if required.

Example structure:

| Scenario | Scenario Probability | Outcome | Conditional Probability | Path Probability |
|---|---:|---|---:|---:|
| Scenario 1 | \(P(S_1)\) | Outcome A | \(P(A \mid S_1)\) | \(P(S_1)P(A \mid S_1)\) |
| Scenario 1 | \(P(S_1)\) | Outcome B | \(P(B \mid S_1)\) | \(P(S_1)P(B \mid S_1)\) |
| Scenario 2 | \(P(S_2)\) | Outcome C | \(P(C \mid S_2)\) | \(P(S_2)P(C \mid S_2)\) |
| Scenario 2 | \(P(S_2)\) | Outcome D | \(P(D \mid S_2)\) | \(P(S_2)P(D \mid S_2)\) |

记忆：

> Branch probability × conditional probability = final path probability.

---

## 15. Bayes' Formula | 贝叶斯公式

Bayes' formula updates probability when new information arrives.

It reverses conditional probability.

普通形式：

$$
\begin{aligned}
P(A \mid B)
&=
\frac{P(B \mid A)P(A)}{P(B)}
\end{aligned}
$$

where:

- \(P(A)\) = prior probability；
- \(P(B \mid A)\) = likelihood；
- \(P(B)\) = unconditional probability of new information；
- \(P(A \mid B)\) = posterior probability。

记忆：

> Bayes' formula updates old belief using new information.

---

## 16. Bayes' Formula with Multiple Scenarios | 多情景贝叶斯公式

If there are several possible scenarios \(S_1, S_2, \ldots, S_n\), then:

$$
\begin{aligned}
P(S_i \mid A)
&=
\frac{
P(A \mid S_i)P(S_i)
}{
\sum_{j=1}^{n} P(A \mid S_j)P(S_j)
}
\end{aligned}
$$

含义：

> Updated probability of a scenario equals the likelihood of new information under that scenario times the prior probability, divided by the total probability of the new information.

记忆：

> Posterior = likelihood × prior / total probability.

---

## 17. Prior, Likelihood, and Posterior | 先验、似然、后验

### Prior Probability

Prior probability is the probability before new information arrives.

Example:

> Before earnings announcement, probability that EPS exceeds consensus is 45%.

### Likelihood

Likelihood is the probability of observing new information given a scenario.

Example:

> Probability that the company expands capacity given EPS exceeded consensus.

### Posterior Probability

Posterior probability is the updated probability after new information arrives.

Example:

> After expansion announcement, updated probability that EPS exceeded consensus.

记忆：

> Prior = before information.  
> Likelihood = probability of information under a scenario.  
> Posterior = after information.

---

## 18. Bayes' Formula Calculation Steps | 贝叶斯计算步骤

### Step 1: Identify the Event of Interest

Example:

> EPS exceeded consensus.

### Step 2: Identify the New Information

Example:

> Company announced capacity expansion.

### Step 3: Write Down Prior Probabilities

$$
\begin{aligned}
P(S_1), P(S_2), \ldots, P(S_n)
\end{aligned}
$$

### Step 4: Write Down Likelihoods

$$
\begin{aligned}
P(A \mid S_1), P(A \mid S_2), \ldots, P(A \mid S_n)
\end{aligned}
$$

### Step 5: Calculate Total Probability of New Information

$$
\begin{aligned}
P(A)
&=
\sum_{i=1}^{n} P(A \mid S_i)P(S_i)
\end{aligned}
$$

### Step 6: Apply Bayes' Formula

$$
\begin{aligned}
P(S_i \mid A)
&=
\frac{
P(A \mid S_i)P(S_i)
}{
P(A)
}
\end{aligned}
$$

记忆：

> Calculate denominator first.  
> Then calculate posterior probability.

---

## 19. Simple Bayes Example | 简单贝叶斯例子

Suppose there are three possible earnings outcomes:

| Scenario | Prior Probability |
|---|---:|
| EPS beats consensus | 0.45 |
| EPS meets consensus | 0.30 |
| EPS misses consensus | 0.25 |

New information:

> The company announces capacity expansion.

Likelihoods:

| Scenario | Probability of Expansion Given Scenario |
|---|---:|
| Beat consensus | 0.75 |
| Meet consensus | 0.20 |
| Miss consensus | 0.05 |

First, calculate the total probability of expansion:

$$
\begin{aligned}
P(\text{Expand})
&=
P(\text{Expand} \mid \text{Beat})P(\text{Beat})
+
P(\text{Expand} \mid \text{Meet})P(\text{Meet})
+
P(\text{Expand} \mid \text{Miss})P(\text{Miss}) \\
&=
0.75(0.45)
+
0.20(0.30)
+
0.05(0.25) \\
&=
0.41
\end{aligned}
$$

Then, calculate the updated probability that EPS beats consensus:

$$
\begin{aligned}
P(\text{Beat} \mid \text{Expand})
&=
\frac{
P(\text{Expand} \mid \text{Beat})P(\text{Beat})
}{
P(\text{Expand})
} \\
&=
\frac{
0.75(0.45)
}{
0.41
} \\
&=
0.8232
\end{aligned}
$$

Interpretation:

> Before the announcement, the probability of beating consensus was 45%.  
> After the expansion announcement, the updated probability is 82.32%.

记忆：

> Posterior probability = likelihood × prior probability / total probability of new information.

## 20. Investment Applications | 投资应用

Probability trees and Bayes' formula are useful in:

- forecasting EPS；
- estimating default recovery；
- credit analysis；
- assessing bond default risk；
- evaluating company announcements；
- updating views after new information；
- scenario analysis；
- portfolio risk analysis；
- investment decision-making under uncertainty。

Examples:

- A bond recovery value depends on economic scenario.
- A company announcement changes EPS expectations.
- A credit score changes repayment probability.
- A bankruptcy model changes default probability.

记忆：

> Investment analysis is about updating probabilities as new information arrives.

---

## 21. Exam Traps | 高频陷阱

- Expected value is probability-weighted, not equally weighted.
- Sample mean is historical; expected value is forward-looking.
- Variance uses squared deviations from expected value.
- Standard deviation is the square root of variance.
- Variance is in squared units.
- Standard deviation is in original units.
- In a probability tree, multiply along branches.
- Across mutually exclusive terminal outcomes, add probabilities.
- Conditional probability is not the same as unconditional probability.
- \(P(A \mid B)\) is not usually equal to \(P(B \mid A)\).
- Total probability rule gives the denominator in Bayes' formula.
- Bayes' formula updates prior probability into posterior probability.
- Likelihood means probability of new information given a scenario.
- Prior probabilities must sum to 1.
- Posterior probabilities must also sum to 1.
- Scenarios should be mutually exclusive and exhaustive.

---

## 22. Quick Review | 考前速记

- Expected value = weighted average outcome.
- Variance = expected squared deviation from expected value.
- Standard deviation = square root of variance.
- Probability tree = visual scenario analysis.
- Conditional probability = probability given another event.
- Total probability = weighted average of conditional probabilities.
- Conditional expected value = expected value under one scenario.
- Bayes' formula = update probability with new information.
- Prior = old probability.
- Likelihood = probability of information under scenario.
- Posterior = updated probability.
- Multiply along probability tree paths.
- Add mutually exclusive final outcomes.
- \(P(A \mid B)\) and \(P(B \mid A)\) are different.

---

## 23. One-Page Formula Sheet

### Expected Value

$$
\begin{aligned}
E(X)
&=
\sum_{i=1}^{n} P(X_i)X_i
\end{aligned}
$$

### Variance

$$
\begin{aligned}
\sigma^2(X)
&=
E\left[(X - E(X))^2\right]
\end{aligned}
$$

### Discrete Variance

$$
\begin{aligned}
\sigma^2(X)
&=
\sum_{i=1}^{n}
P(X_i)
\left[
X_i - E(X)
\right]^2
\end{aligned}
$$

### Standard Deviation

$$
\begin{aligned}
\sigma(X)
&=
\sqrt{\sigma^2(X)}
\end{aligned}
$$

### Conditional Probability

$$
\begin{aligned}
P(A \mid B)
&=
\frac{P(A \cap B)}{P(B)}
\end{aligned}
$$

### Total Probability Rule

$$
\begin{aligned}
P(A)
&=
\sum_{i=1}^{n} P(A \mid S_i)P(S_i)
\end{aligned}
$$

### Conditional Expected Value

$$
\begin{aligned}
E(X \mid S)
&=
\sum_{i=1}^{n} P(X_i \mid S)X_i
\end{aligned}
$$

### Total Probability Rule for Expected Value

$$
\begin{aligned}
E(X)
&=
\sum_{i=1}^{n} E(X \mid S_i)P(S_i)
\end{aligned}
$$

### Conditional Variance

$$
\begin{aligned}
\sigma^2(X \mid S)
&=
\sum_{i=1}^{n}
P(X_i \mid S)
\left[
X_i - E(X \mid S)
\right]^2
\end{aligned}
$$

### Bayes' Formula

$$
\begin{aligned}
P(A \mid B)
&=
\frac{P(B \mid A)P(A)}{P(B)}
\end{aligned}
$$

### Bayes' Formula with Multiple Scenarios

$$
\begin{aligned}
P(S_i \mid A)
&=
\frac{
P(A \mid S_i)P(S_i)
}{
\sum_{j=1}^{n} P(A \mid S_j)P(S_j)
}
\end{aligned}
$$
