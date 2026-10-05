# DSCI 552 — Homework 3

## 1. Time Series Classification Part 1: Feature Creation/Extraction

An interesting task in machine learning is the classification of time series. In
this problem, we will classify human activities based on time series obtained from
a Wireless Sensor Network.

### (a) AReM Dataset

Download the
[AReM dataset](https://archive.ics.uci.edu/dataset/366/activity+recognition+system+based+on+multisensor+data+fusion+arem).

The dataset contains seven folders representing seven types of activities. Each
folder contains multiple files, where each file represents an instance of a human
performing an activity. Each file contains six time series collected from the
activities of the same person:

- `avg_rss12`
- `var_rss12`
- `avg_rss13`
- `var_rss13`
- `avg_rss23`
- `var_rss23`

There are 88 instances in the dataset. Each instance contains six time series,
and each time series has 480 consecutive values.

### (b) Training and Test Data

Create the test set using:

- Datasets 1 and 2 from `bending1`
- Datasets 1 and 2 from `bending2`
- Datasets 1, 2, and 3 from every other activity folder

Use all remaining datasets as training data.

### (c) Feature Extraction

Time-series classification usually requires extracting features from each time
series. In this problem, focus on time-domain features.

#### (i) Common Time-Domain Features

Research and list the types of time-domain features commonly used in time-series
classification, such as minimum, maximum, and mean.

#### (ii) Extracted Time-Domain Features

For each of the six time series in every instance, extract the following features:

1. Minimum
2. Maximum
3. Mean
4. Median
5. Standard deviation
6. First quartile
7. Third quartile

The features may be normalized or standardized, or they may be used directly.

The resulting dataset should have the following general structure:

| Instance | min1 | max1 | mean1 | median1 | ... | 1st_quart6 | 3rd_quart6 |
|---------:|-----:|-----:|------:|--------:|----:|-----------:|-----------:|
| 1        |      |      |       |         |     |            |            |
| 2        |      |      |       |         |     |            |            |
| 3        |      |      |       |         |     |            |            |
| ...      |      |      |       |         |     |            |            |
| 88       |      |      |       |         |     |            |            |

For example, `1st_quart6` is the first quartile of the sixth time series for each
of the 88 instances.

#### (iii) Bootstrap Confidence Intervals

Estimate the standard deviation of each extracted time-domain feature. Then use
Python's bootstrap method, or another appropriate method, to construct a 90%
bootstrap confidence interval for the standard deviation of each feature.

#### (iv) Important Features

Use your judgment to select the three most important time-domain features. One
possible selection is minimum, mean, and maximum.

## 2. ISLR 3.7.4

Complete Exercise 3.7.4 from *An Introduction to Statistical Learning* (ISLR).