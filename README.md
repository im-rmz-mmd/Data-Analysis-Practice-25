# 🎮 Video Game Sales Dashboard | Power BI Project

This project analyzes video game sales data, uncovering key insights about top publishers, popular genres, and sales trends across regions and time.

---

## 📁 Dataset & Preparation

Using Python and Pandas:

- Removed irrelevant column (`Rank`)
- Dropped duplicates and missing values
- Exported a clean dataset to Excel and loaded it into Power BI

---

## 🔗 Data Model

Single-table model: `Cleaned_vgsale`

No relationships required – all columns handled within one cleaned dataset.

---

## 🧮 DAX Measures – KPI Cards

```dax
-- 1. Total Global Sales
Total Global Sales = SUM(Cleaned_vgsale[Global_Sales])

-- 2. Total Games
Total Games = COUNTROWS(Cleaned_vgsale)

-- 3. Top Publisher
Top Publisher = 
CALCULATE(
    FIRSTNONBLANK(Cleaned_vgsale[Publisher], 1),
    TOPN(1, VALUES(Cleaned_vgsale[Publisher]), [Total Global Sales])
)

-- 4. Most Popular Genre
Most Popular Genre = 
CALCULATE(
    FIRSTNONBLANK(Cleaned_vgsale[Genre], 1),
    TOPN(1, VALUES(Cleaned_vgsale[Genre]), [Total Global Sales])
)
```

---

## 📊 Visuals in the Dashboard

### 🔹 KPI Cards:
- **Total Global Sales** (8,811.97 M)
- **Total Games** (16K)
- **Top Publisher** (Nintendo)
- **Most Popular Genre** (Action)

---

### 🔹 Charts:

1. **Horizontal Bar Chart** – `Sum of Global Sales by Name`  
   → Shows top-selling individual games.

2. **Column Chart** – `Sum of Global Sales by Year`  
   → Reveals sales trends over the years.

3. **Donut Chart** – `Sum of Global Sales by Genre`  
   → Displays market share by genre.

4. **Stacked Bar Chart** – `Sum of Regional Sales by Genre`  
   → Compares NA, EU, JP, and Other sales for each genre.

5. **Treemap** – `Sum of Global Sales by Publisher`  
   → Visualizes publisher contributions.

---

## 💡 Business Insight

This dashboard helps stakeholders:

- Identify top genres and publishers
- Understand regional sales performance
- Monitor yearly trends in game popularity
- Make strategic decisions in marketing and development

---

👉 Feel free to fork, customize, and use this in your own portfolio.
