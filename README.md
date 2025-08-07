# 📊 2024 Company Financial Overview – Power BI Dashboard

## 📌 Project Summary
This Power BI dashboard provides a comprehensive overview of company financials for the year 2024. It tracks key performance indicators such as revenue, expenses, profit, and daily averages, enabling stakeholders to monitor financial health and spending patterns across departments.

---

## 🧰 Tools Used
- Microsoft Power BI
- Excel (for data source: `Company_Financial_Transactions_2024.xlsx`)
- DAX for measures and calculations

---

## 📁 Data Overview

**Main Dataset:**
- `Date`
- `Department`
- `Category` (Revenue / Expense)
- `Sub_Category` (e.g., Salaries, Rent, Product Sales)
- `Amount` (positive for revenue, negative for expense)

**Extra Table Created:**
- `DateTable` – full calendar table with:
  - `Date`
  - `IsWeekday` (TRUE/FALSE)

---

## 🧮 Measures Created (DAX)

```DAX
Total Revenue = 
CALCULATE(SUM(Transactions[Amount]), Transactions[Category] = "Revenue")

Total Expenses = 
CALCULATE(SUM(Transactions[Amount]), Transactions[Category] = "Expense")

Net Profit = 
[Total Revenue] + [Total Expenses]

Weekday Count = 
CALCULATE(COUNTROWS(DateTable), DateTable[IsWeekday] = TRUE())

Average Weekday Revenue = 
DIVIDE([Total Revenue], [Weekday Count])



This dashboard demonstrates the use of Power BI for real-world financial monitoring. It combines DAX, time intelligence, and interactivity to support informed decision-making by business leaders.
