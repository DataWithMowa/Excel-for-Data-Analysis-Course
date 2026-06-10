# Statistical Functions for Data Analysis — Dialogue

## Objectives

- Understanding the limitations of surface-level analysis
- Identifying the need for structured analysis
- Connecting business questions to data analysis functions

---

## The Dialogue

**Prompt:** Imagine a scenario: Your manager rushes over to you and says, *"Quick! How did sales do last quarter?"* You have a spreadsheet with hundreds of sales figures. What's the very first thing you would do or think about to answer your manager's question?

---

**Q:** If your manager wants to know *"How did sales do last quarter?"* in a general sense, would just the highest number give them the full picture of overall performance? What other single number might give a more representative summary of all the sales from the entire quarter?

**A:** Average sales, total sales.

---

**Q:** Excellent! You've hit on two very common and useful ways to summarize sales data. Now, which of those two — average sales or total sales — do you think would be more immediately informative for understanding the typical performance or the overall volume?

**A:** Average sales.

---

**Q:** You're right. Average sales can be very informative for understanding typical performance. Now, imagine you calculate the average sales for last quarter and tell your manager, *"Our average sale was $4,500."* Is there anything about just that single average number that might not tell the whole story, or could even be misleading?

> **Note:** While an average is great for a quick summary, it can sometimes hide important details. For example, what if you had one huge sale of $100,000 and many small sales of $100? The average might look high, but it wouldn't represent the typical sale very well. This is where outliers can skew the average.

**Q:** With that in mind, can you think of another single number that might give a different, perhaps more "typical" view of sales — especially if there are some very high or very low figures pulling the average in one direction?

**A:** The median sale.

---

**Q:** Exactly! Can you explain in your own words why the median might give a more "typical" view of sales compared to the average, especially in a situation with outliers?

**A:** The median gives you the middle value of a dataset when all the values are arranged in order from smallest to largest.

For example:

```
3, 7, 9, 15, 22
```

The median is **9** — it sits right in the middle.

The median is useful because it ignores extreme values (outliers). For example, imagine 5 people's salaries:

```
₦50k, ₦60k, ₦65k, ₦70k, ₦900k
```

- **Mean:** ~₦229k — pulled way up by the ₦900k outlier, not representative
- **Median:** ₦65k — a far more accurate picture of typical earnings

**Rule of thumb:** When data has outliers or is skewed, use the **median**. When the data is fairly even, the **mean** works fine.

The median will give us the middle value of the sales figures. It ignores outliers, it is more honest and will give us a better representation of the whole figures — something the mean value wouldn't.

---

**Q:** Now, what if your manager asked, *"How many of our sales last quarter were over $10,000?"* Which type of function do you think would be most useful for answering a question like that? How would you count how many times that condition is met across all your sales figures in a spreadsheet?

**A:** The function is **COUNTIF**. It counts cells, but only if they meet a condition you specify.

```excel
=COUNTIF(A2:A100, ">10000")
```

This tells Excel: *"Go through all the sales figures in cells A2 to A100, and count every cell where the value is greater than 10,000."*

Breaking it down:
- `A2:A100` — the range of cells to check (the sales figures)
- `">10000"` — the condition (greater than $10,000)

> **Bonus:** To *add up* all sales over $10,000 instead of just counting them, use **SUMIF** — same logic, but it sums the values rather than counts them.

---

> **Summary:** You've successfully demonstrated how to translate a specific business question — *"How many of our sales last quarter were over $10,000?"* — into a precise data analysis function using COUNTIF.
