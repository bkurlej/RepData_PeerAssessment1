# Reproducible Research: Peer Assessment 1


## Loading and preprocessing the data
Extract and load data to df variable

```r
unzip("activity.zip")
df <- read.csv("activity.csv")
```

## What is mean total number of steps taken per day?

First sum up all steps by days (missing values are omited)

```r
aggregatedTotalStepsByDay = aggregate(steps~date,data = df,sum)
```
Then produce histogram

```r
hist(aggregatedTotalStepsByDay$steps,
     xlab = "Total Steps by day",
     main = "Histogram of Total Steps by day")
```

![](./PA1_template_files/figure-html/unnamed-chunk-2-1.png) 

And compute mean and median:

```r
meanOfTotalStepsByDay = mean(aggregatedTotalStepsByDay$steps)
medianOfTotalStepsByDay = median(aggregatedTotalStepsByDay$steps)
```

The total steps by day **mean** is 1.0766189\times 10^{4} and  
the total steps by day **median** is 10765

## What is the average daily activity pattern?

First agregate all steps by interval (missing values are omited)

```r
aggregatedTotalStepsByInterval = aggregate(steps~interval,data = df,mean)
```

Plot of result

```r
plot(aggregatedTotalStepsByInterval, 
     type="l", 
     main="Daily activity")
```

![](./PA1_template_files/figure-html/unnamed-chunk-5-1.png) 

Compute interval with maximum avarange steps:

```r
intervalWithMaxSteps = 
    aggregatedTotalStepsByInterval$interval[which.max(aggregatedTotalStepsByInterval$steps)]
```

The interval with maximum avarange of steps is 835th 
5min interval in the day.
## Imputing missing values
aa
asdf

## Are there differences in activity patterns between weekdays and weekends?
asdf
