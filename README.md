# Excel Assignment: Moving Average Crossover Signal Generator

## Overview
In this assignment, you will use **Microsoft Excel (or Google Sheets)** to analyze trading data and generate **buy signals** based on a **moving average crossover strategy**.

**Time Allocation:** Up to **2 hours**

**Tools Allowed:**  
You may use **Excel or Google Sheets**, **online tutorials**, or **AI assistants** to help with formulas, charting, and analysis.  
This is a **practical data analysis exercise** — we want to see your problem-solving and reasoning approach, not programming.

---

## Part 1: Understanding the Problem (15–20 minutes)

Before working in Excel, you’ll explain your understanding of the moving average crossover concept and how you’ll apply it in a spreadsheet.

### Your Task

1. **Moving Average Crossover Strategy**
   - What is a **Simple Moving Average (SMA)**?
   - What does a **“crossover”** mean in trading?
   - How can we use this crossover to create a **buy signal**?
   - What are typical **parameters** (e.g., 5-day vs. 20-day averages)?

2. **Data Processing**
   - Which data columns from the CSV are relevant (e.g., time, price)?

3. **Output**
   - What should your final Excel table include?
   - How will you indicate a **buy signal** in the results?

### Deliverable
You should be able to explain (or write down briefly):
- How you calculate the moving averages  
- When a buy signal is triggered  
- What columns will appear in your final table  

You may proceed to Part 2 once you clearly understand these concepts.

---

## Part 2: Excel Implementation (90–100 minutes)

### Input Data
You’ll receive trading data in **CSV format**, with columns like:

| block_time | block_num | price_in_sol | ... other data ... |
|-------------|------------|---------------|--------------------|
| 1757782395 | 366586929 | 0.0000000283 | ... |

Only the **block_time**, **block_num**, and **price_in_sol** fields are required for your analysis.

---

### Your Excel Tasks

1. **Import the CSV file**
   - Open it in Excel or Google Sheets
   - Ensure data is sorted by **block_time (oldest to newest)**

2. **Calculate Moving Averages**
   - Create two new columns:
     - **Short Moving Average (SMA_short)**: average of the last **5** prices  
     - **Long Moving Average (SMA_long)**: average of the last **20** prices  
   - Use Excel’s `AVERAGE()` function and relative cell ranges.  
     Example formula (for row 25):  
     ```
     =AVERAGE(C21:C25)
     ```

3. **Detect Buy Signals**
   - Create a new column called **Signal**
   - A **BUY_SIGNAL** occurs when the short MA **crosses above** the long MA  
     (i.e., when short MA > long MA, and the previous row short MA ≤ previous long MA)
   - You can use an `IF()` formula like:  
     ```
     =IF(AND(D25>E25, D24<=E24), "BUY_SIGNAL", "")
     ```

4. **Prepare the Output Table**
   - Keep only rows with a “BUY_SIGNAL”
   - Include these columns in your final table:
     - **block_num**  
     - **timestamp** (from block_time)  
     - **signal** (“BUY_SIGNAL”)

5. **Save as Parquet or Excel File**
   - Save your final sheet as `crypto-signals.xlsx` (or if you prefer, `.csv`)  
   - Parquet file output is not required — Excel output is sufficient.

---

## Evaluation Criteria

You will be evaluated on:

- **Correctness:** Are the moving averages and signals calculated correctly?  
- **Presentation:** Is your sheet well-organized and easy to read?  
- **Reasoning:** Can you explain how you determined buy signals?  
- **Communication:** Are your explanations clear and logical?

---

## Tips

- Start simple: calculate the 5-day average first, then add the 20-day one.  
- Use Excel formulas to check when a crossover happens.  
- Use **charts** to visualize the two moving averages and highlight buy signals (optional, but recommended).  
- Use color formatting to make signals stand out.

---

## Submission

When finished, be prepared to:

1. Show your **Excel sheet** with calculated moving averages and buy signals  
2. Explain why you chose your short and long MA periods  
3. Walk through one or two example signals  
4. Discuss any challenges and how you solved them

---

✅ **Goal:** Demonstrate that you can use Excel to apply a trading analysis technique, interpret data trends, and generate meaningful insights — no coding required.
