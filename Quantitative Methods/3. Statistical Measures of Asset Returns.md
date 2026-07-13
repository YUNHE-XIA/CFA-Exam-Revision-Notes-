# Statistical Measures of Asset Returns | 资产收益率的统计度量

## 1. 核心记忆

This reading focuses on how to summarize and analyze financial return data.

本章主要学习如何描述和分析资产收益率数据，包括：

- central tendency：数据中心位置；
- location：数据分布位置；
- dispersion：数据波动程度；
- skewness：分布是否对称；
- kurtosis：尾部风险是否更高；
- covariance and correlation：两个变量如何一起变动。

投资分析中，这些统计指标可以帮助我们理解：

- expected return；
- risk；
- downside risk；
- distribution shape；
- diversification benefit。

记忆：

> Mean tells us return.  
> Dispersion tells us risk.  
> Skewness and kurtosis tell us the shape of risk.  
> Correlation tells us diversification potential.

---

## 2. Measures of Central Tendency | 集中趋势

Measures of central tendency describe where the data are centered.

常见指标：

- mean；
- median；
- mode。

---

## 3. Arithmetic Mean | 算术平均数

Arithmetic mean 是最常用的平均数。

$$
\bar{X} = \frac{\sum_{i=1}^{n} X_i}{n}
$$

含义：

> Sum of all observations divided by number of observations.

优点：

- easy to calculate；
- uses all observations；
- commonly used in investment analysis。

缺点：

- sensitive to outliers；
- extreme values can pull the mean upward or downward。

记忆：

> Mean is useful, but outliers can distort it.

---

## 4. Median | 中位数

Median is the middle value after sorting data.

如果样本数量是奇数：

$$
Median = \text{middle observation}
$$

如果样本数量是偶数：

$$
Median = \frac{\text{two middle observations}}{2}
$$

优点：

- not affected by extreme values；
- useful for skewed distributions。

缺点：

- does not use all information；
- less mathematically convenient than mean。

记忆：

> Median is better when data are skewed or have outliers.

---

## 5. Mode | 众数

Mode is the most frequently occurring value.

可能出现：

- unimodal：one mode；
- bimodal：two modes；
- trimodal：three modes；
- no mode：no value appears more frequently。

Mode 的特点：

> It is the only measure of central tendency that can be used with nominal or categorical data.

记忆：

> Mode = most common value.

---

## 6. Outliers | 异常值

Outliers are extreme observations.

处理方式：

1. Do nothing；
2. Delete outliers；
3. Replace outliers with another value。

### Trimmed Mean

Trimmed mean removes a small percentage of the lowest and highest values.

例如：

> 5% trimmed mean removes the lowest 2.5% and highest 2.5%.

### Winsorized Mean

Winsorized mean replaces extreme values with specified boundary values.

例如：

> 95% winsorized mean replaces the bottom 2.5% and top 2.5% with cutoff values.

记忆：

> Trimmed mean deletes outliers.  
> Winsorized mean replaces outliers.

---

## 7. Measures of Location | 位置度量

Measures of location describe where observations fall within a distribution.

常见 quantiles：

| Measure | 中文 | Divides Data Into |
|---|---|---|
| Quartiles | 四分位数 | 4 parts |
| Quintiles | 五分位数 | 5 parts |
| Deciles | 十分位数 | 10 parts |
| Percentiles | 百分位数 | 100 parts |

Median is the 50th percentile.

---

## 8. Interquartile Range | 四分位距

Interquartile range measures the spread of the middle 50% of data.

$$
IQR = Q_3 - Q_1
$$

含义：

- Q1 = first quartile；
- Q3 = third quartile；
- IQR excludes extreme tails。

记忆：

> IQR measures the spread of the middle half of the data.

---

## 9. Box and Whisker Plot | 箱线图

Box and whisker plot shows data distribution visually.

通常包括：

- minimum；
- Q1；
- median；
- Q3；
- maximum；
- outliers。

The box represents:

$$
Q_1 \text{ to } Q_3
$$

The height of the box is:

$$
IQR = Q_3 - Q_1
$$

Outlier fences are often:

$$
Upper\ Fence = Q_3 + 1.5 \times IQR
$$

$$
Lower\ Fence = Q_1 - 1.5 \times IQR
$$

记忆：

> Box shows the middle 50%.  
> Whiskers show the wider range.  
> Points outside fences may be outliers.

---

## 10. Measures of Dispersion | 离散程度

Dispersion measures variability around the mean.

投资中：

> Expected return measures reward.  
> Dispersion measures risk.

常见 dispersion measures：

- range；
- mean absolute deviation；
- variance；
- standard deviation；
- downside deviation；
- coefficient of variation。

---

## 11. Range | 极差

Range is the difference between maximum and minimum values.

$$
Range = Maximum - Minimum
$$

优点：

- easy to calculate。

缺点：

- uses only two observations；
- sensitive to outliers；
- does not describe the full distribution。

记忆：

> Range is simple but limited.

---

## 12. Mean Absolute Deviation | 平均绝对偏差

MAD measures the average absolute distance from the mean.

$$
MAD = \frac{\sum_{i=1}^{n} |X_i - \bar{X}|}{n}
$$

优点：

- uses all observations；
- avoids positive and negative deviations canceling out。

缺点：

- less mathematically convenient than variance。

记忆：

> MAD uses absolute deviations from the mean.

---

## 13. Sample Variance | 样本方差

Variance measures average squared deviation from the mean.

$$
s^2 =
\frac{\sum_{i=1}^{n}(X_i - \bar{X})^2}{n-1}
$$

注意：

> Sample variance divides by n - 1, not n.

原因：

> n - 1 is degrees of freedom.

记忆：

> Variance squares the deviations.

---

## 14. Sample Standard Deviation | 样本标准差

Standard deviation is the square root of variance.

$$
s =
\sqrt{
\frac{\sum_{i=1}^{n}(X_i - \bar{X})^2}{n-1}
}
$$

优点：

- same unit as original data；
- easier to interpret than variance；
- widely used as a measure of risk。

记忆：

> Standard deviation measures how far returns move around the mean.

---

## 15. Target Downside Deviation | 目标下行偏差

Target downside deviation measures downside risk below a target return.

If target return is B:

$$
s_{Target}
=
\sqrt{
\frac{\sum (X_i - B)^2}{n-1}
}
$$

Only observations below the target are included in the numerator.

含义：

> It focuses only on bad outcomes below the target.

记忆：

> Standard deviation counts upside and downside risk.  
> Target downside deviation counts only downside risk.

---

## 16. Coefficient of Variation | 变异系数

Coefficient of variation measures risk per unit of return.

$$
CV = \frac{s}{\bar{X}}
$$

含义：

> Standard deviation divided by mean.

用途：

- compare dispersion across different datasets；
- useful when datasets have different means or units；
- scale-free measure。

注意：

> If the mean is negative, CV is not meaningful.

记忆：

> CV = risk per unit of reward.  
> Lower CV is better if comparing return efficiency.

---

## 17. Skewness | 偏度

Skewness measures asymmetry of a distribution.

### Positive Skewness

Positive skew means:

- frequent small losses；
- few extreme gains；
- long right tail。

一般关系：

$$
Mode < Median < Mean
$$

投资者通常喜欢 positive skew because there is upside tail potential.

### Negative Skewness

Negative skew means:

- frequent small gains；
- few extreme losses；
- long left tail。

一般关系：

$$
Mean < Median < Mode
$$

投资者通常不喜欢 negative skew because there is downside tail risk.

### Zero Skewness

Zero skewness means:

> symmetric distribution.

记忆：

> Positive skew = chance of large upside.  
> Negative skew = risk of large downside.

---

## 18. Kurtosis | 峰度 / 尾部厚度

Kurtosis measures the combined weight of the tails of a distribution.

Normal distribution has:

$$
Kurtosis = 3
$$

Excess kurtosis:

$$
Excess\ Kurtosis = Kurtosis - 3
$$

---

## 19. Types of Kurtosis

| Kurtosis | Excess Kurtosis | Distribution | 中文理解 |
|---|---:|---|---|
| > 3 | > 0 | Leptokurtic / Fat-tailed | 厚尾 |
| = 3 | = 0 | Mesokurtic | 类似正态分布 |
| < 3 | < 0 | Platykurtic / Thin-tailed | 薄尾 |

Fat-tailed distribution means:

> More frequent extreme outcomes than normal distribution.

记忆：

> Positive excess kurtosis = fat tails = more extreme events.

---

## 20. Normal Distribution | 正态分布

Normal distribution has these features:

- symmetric；
- bell-shaped；
- mean = median = mode；
- fully described by mean and variance。

记忆：

> Normal distribution is completely described by mean and variance.  
> But financial returns are often not perfectly normal.

---

## 21. Covariance | 协方差

Covariance measures how two variables move together.

$$
s_{XY}
=
\frac{
\sum_{i=1}^{n}
(X_i - \bar{X})(Y_i - \bar{Y})
}{n-1}
$$

If covariance is positive:

> X and Y tend to move in the same direction.

If covariance is negative:

> X and Y tend to move in opposite directions.

缺点：

> The magnitude of covariance is hard to interpret because it depends on units.

记忆：

> Covariance shows direction, but correlation is easier to interpret.

---

## 22. Correlation | 相关系数

Correlation standardizes covariance.

$$
r_{XY}
=
\frac{s_{XY}}{s_X s_Y}
$$

Range:

$$
-1 \le r_{XY} \le 1
$$

Interpretation:

| Correlation | Meaning |
|---:|---|
| +1 | Perfect positive linear relationship |
| Close to +1 | Strong positive relationship |
| 0 | No linear relationship |
| Close to -1 | Strong negative relationship |
| -1 | Perfect negative linear relationship |

记忆：

> Correlation measures linear association.

---

## 23. Scatter Plot | 散点图

Scatter plot shows the relationship between two variables visually.

It can help identify:

- positive relationship；
- negative relationship；
- no clear relationship；
- nonlinear relationship；
- outliers。

Tight clustering around a line means:

> stronger linear relationship.

Loose clustering means:

> weaker relationship.

记忆：

> Always look at the scatter plot, not only the correlation number.

---

## 24. Limitations of Correlation | 相关系数的局限

Correlation has several limitations:

- correlation does not imply causation；
- it only measures linear relationships；
- nonlinear relationships may have low correlation；
- outliers can distort correlation；
- spurious correlation may appear by chance；
- same correlation can hide very different data patterns。

Spurious correlation means:

> two variables appear related, but the relationship is not economically meaningful.

记忆：

> High correlation does not mean one variable causes the other.

---

## 25. Investment Use | 投资应用

These statistical measures are useful for:

- summarizing return data；
- comparing fund performance；
- ranking assets by quantile；
- identifying downside risk；
- assessing tail risk；
- understanding diversification；
- analyzing portfolio risk；
- detecting outliers；
- evaluating investment strategies。

Examples:

- mean return measures expected reward；
- standard deviation measures volatility；
- downside deviation focuses on bad outcomes；
- skewness shows upside or downside tail risk；
- kurtosis shows extreme event risk；
- correlation helps portfolio diversification。

---

## 26. Exam Traps | 高频陷阱

- Mean is sensitive to outliers.
- Median is better for skewed data.
- Mode is the most frequent value.
- Mode can be used with categorical data.
- A dataset can have more than one mode.
- Trimmed mean deletes outliers.
- Winsorized mean replaces outliers.
- Quartiles divide data into four parts.
- Percentiles divide data into 100 parts.
- IQR = Q3 - Q1.
- Range uses only maximum and minimum.
- Sample variance divides by n - 1.
- Standard deviation is in the same unit as data.
- Variance is in squared units.
- Target downside deviation focuses only on returns below the target.
- CV = standard deviation / mean.
- CV is meaningless if mean is negative.
- Positive skew has a long right tail.
- Negative skew has a long left tail.
- Normal distribution has kurtosis of 3.
- Excess kurtosis of normal distribution is 0.
- Positive excess kurtosis means fat tails.
- Correlation ranges from -1 to +1.
- Correlation measures linear association only.
- Correlation does not imply causation.
- Outliers can distort correlation.
- Spurious correlation can mislead investors.

---

## 27. Quick Review | 考前速记

- Mean = average return.
- Median = middle value.
- Mode = most frequent value.
- Median is useful when data are skewed.
- Trimmed mean removes extreme values.
- Winsorized mean replaces extreme values.
- Quantiles divide ranked data into groups.
- IQR measures middle 50% spread.
- Range = max - min.
- MAD = average absolute deviation from mean.
- Variance = average squared deviation.
- Standard deviation = square root of variance.
- Sample variance uses n - 1.
- Downside deviation measures risk below target.
- CV = risk per unit of return.
- Positive skew = small losses and extreme gains.
- Negative skew = small gains and extreme losses.
- Kurtosis measures tail weight.
- Fat tails mean more extreme outcomes.
- Covariance shows whether variables move together.
- Correlation standardizes covariance.
- Correlation helps understand diversification.
- Correlation does not mean causation.

---

## 28. One-Page Formula Sheet

### Arithmetic Mean

$$
\bar{X} = \frac{\sum_{i=1}^{n} X_i}{n}
$$

### Range

$$
Range = Maximum - Minimum
$$

### Interquartile Range

$$
IQR = Q_3 - Q_1
$$

### Mean Absolute Deviation

$$
MAD = \frac{\sum_{i=1}^{n} |X_i - \bar{X}|}{n}
$$

### Sample Variance

$$
s^2 =
\frac{\sum_{i=1}^{n}(X_i - \bar{X})^2}{n-1}
$$

### Sample Standard Deviation

$$
s =
\sqrt{
\frac{\sum_{i=1}^{n}(X_i - \bar{X})^2}{n-1}
}
$$

### Coefficient of Variation

$$
CV = \frac{s}{\bar{X}}
$$

### Sample Covariance

$$
s_{XY}
=
\frac{
\sum_{i=1}^{n}
(X_i - \bar{X})(Y_i - \bar{Y})
}{n-1}
$$

### Sample Correlation

$$
r_{XY}
=
\frac{s_{XY}}{s_X s_Y}
$$

### Excess Kurtosis

$$
Excess\ Kurtosis = Kurtosis - 3
$$
