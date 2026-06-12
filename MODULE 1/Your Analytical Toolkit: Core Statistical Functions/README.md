This is basically a guide to four spreadsheet/statistics tools that help you make sense of data. Here's the simple breakdown:

**AVERAGE** – adds up all your numbers and divides by how many there are, giving you the "typical" value. Example: average daily steps from fitness tracker data tells you how active users generally are.

**MEDIAN** – the middle value when you line up all your numbers from smallest to largest. It's useful because it doesn't get thrown off by extreme outliers. Example: if 9 taxi rides cost $10-15 but one costs $200, the average would look misleadingly high, but the median would still show you the "normal" fare.

**STDEV (Standard Deviation)** – tells you how spread out your data is. Low STDEV = most values are close to the average (consistent). High STDEV = values are all over the place (inconsistent). Example: if taxi fares have a high STDEV, it means some rides are cheap and others are very expensive, with not much consistency.

**COUNTIF** – counts how many entries in your data meet a condition you set. Example: counting how many fitness tracker users walked more than 12,000 steps in a day, so you can identify your "highly active" users.

**The big picture:** these four functions are basic but powerful tools for spotting patterns in data — the typical value (AVERAGE/MEDIAN), how consistent or variable things are (STDEV), and how many things meet a certain criteria (COUNTIF). The article uses two real datasets (NYC taxi trips and Bellabeat fitness data) just as examples of where you'd actually apply these.

Let's use a simple example with daily step counts from a fitness tracker (like Bellabeat), since that's easy to visualize. Imagine we have 10 days of step data for one user:

```
Day 1: 8,000
Day 2: 12,500
Day 3: 5,200
Day 4: 15,000
Day 5: 9,800
Day 6: 11,200
Day 7: 6,500
Day 8: 13,800
Day 9: 7,900
Day 10: 22,000  ← this day they ran a marathon (outlier)
```

**1. AVERAGE**

Add all values, divide by 10:

8000+12500+5200+15000+9800+11200+6500+13800+7900+22000 = 111,900

111,900 ÷ 10 = **11,190 steps**

So on average, this person walks about 11,190 steps a day.

**2. MEDIAN**

First, sort the values from smallest to largest:

5200, 6500, 7900, 8000, 9800, 11200, 12500, 13800, 15000, 22000

With 10 values (even number), the median is the average of the two middle numbers (5th and 6th):

(9800 + 11200) ÷ 2 = **10,500 steps**

Notice this is lower than the average (11,190). That's because the 22,000-step marathon day pulled the average up, but the median ignores that and shows what's more "typical."

**3. STDEV**

This one's more involved, but the idea is: how far, on average, does each value stray from the mean (11,190)?

Without going through every step of the math, if you ran this in Excel/Sheets with `=STDEV(range)`, you'd get something like **~4,800 steps**.

What does that tell you? A standard deviation of ~4,800 on a mean of ~11,190 is fairly large — meaning this person's activity is quite inconsistent day to day (some lazy days, some very active days).

**4. COUNTIF**

Let's say you want to know: how many days did this person hit the "highly active" threshold of 12,000+ steps?

Looking at our list: 12,500, 15,000, 13,800, 22,000 → that's **4 days**.

In Excel, the formula would be:
```
=COUNTIF(A1:A10, ">12000")
```

This returns **4**.

---

**Putting it together:** if you were doing a Bellabeat-style analysis, you might say: "This user averages ~11,190 steps/day (median ~10,500), but with high variability (STDEV ~4,800), and only hits the highly-active threshold (12k+ steps) 4 out of 10 days." That's a much richer picture than just one number alone.
