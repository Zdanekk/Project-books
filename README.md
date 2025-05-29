# 📚 Book Purchase Profitability Analysis

This project compares **three purchasing strategies** for school books across multiple online bookstores:

1. **Single-store purchase** – Buy all books from one bookstore (one shipping fee).
2. **Split-by-book purchase** – Buy each book from the cheapest available store (multiple shipping fees).
3. **Optimal mixed-store combination** – Choose the cheapest possible mix (e.g. 2+2 books from different stores) taking into account:
   - Book prices
   - Shipping costs
   - Active promotions

The logic also applies real-world bookstore promotions such as:

- Free shipping thresholds
- Percentage discounts (e.g. -10% from 3 books)
- Bundle offers (e.g. 3 for 2 or buy one, get one free)

---

## 📁 Project Structure

Folders and files:

- `Data/Lektury_szkolne_baza.xlsx` – book prices and shipping info
- `Data/promocje_księgarnie.xlsx` – discount formulas per bookstore (Python expressions)
- `Notebooks/Project.ipynb` – main Jupyter Notebook with logic, tests, and visualizations
- `README.md` – this file

---

## 📊 Input Data

### `Lektury_szkolne_baza.xlsx`

Contains books with their prices and shipping costs per bookstore.

Example:

| Store ID | Book Title                                     | Price    | Shipping |
|----------|------------------------------------------------|----------|----------|
| 1        | Opowieści z Narnii: Lew, czarownica...         | 27.50 zł | 13 zł    |
| 2        | Mały Książę                                    | 20.50 zł | 15 zł    |

### `promocje_księgarnie.xlsx`

Contains promotion formulas in Python, applied only if conditions are met.

Example:

| Store ID | Promotion Name            | Formula                                      |
|----------|---------------------------|----------------------------------------------|
| 1        | Free shipping over 100 zł | `if total_price >= 100: shipping_cost = 0`   |
| 3        | 3 for 2                   | `total_price -= sum(prices[:len(prices)//3])`|

---

## ▶️ How to Run the Notebook

1. Open `Notebooks/Project.ipynb` in Jupyter Notebook.
2. Ensure both Excel files are present in the `Data/` folder.
3. Execute the notebook step-by-step:
   - Load and normalize data
   - Parse and assign promotion formulas
   - Run test cases
   - Compare three strategies
   - Generate summary bar chart

---

## 🧪 Test Cases

The notebook includes 5 defined test sets:

**Test 1 – School Basics**
- Opowieści z Narnii
- W pustyni i w puszczy
- Akademia pana Kleksa
- Chłopcy z Placu Broni

**Test 2 – Extended Set**
- Mały Książę
- Balladyna
- Pan Tadeusz
- Latarnik

**Test 3 – Full Class Set**
- Syzyfowe prace
- Zemsta
- Katarynka
- Kamienie na szaniec

**Test 4 – Minimal Basket**
- Balladyna
- Latarnik

**Test 5 – Max Value Basket**
- Opowieści z Narnii
- Pan Tadeusz
- Akademia pana Kleksa
- Zemsta
- Syzyfowe prace

Each test prints:
- Bookstore assignments
- Promotions used (if applicable)
- Total price per strategy

---

## 📈 Chart Comparison

The notebook ends with a bar chart that visually compares the three strategies:

- **Option 1:** All books in one bookstore
- **Option 2:** Cheapest price per book (split orders)
- **Option 3:** Optimized mix (best combo with working promotions)

You can adjust test sets or extend the list for your own analysis.

---

## 🧰 Technologies Used

- Python 3.12+
- Jupyter Notebook
- Pandas – for data handling
- Matplotlib – for visualization

---

## 🚀 Possible Extensions

- Export results to `.csv` or `.xlsx`
- Add an interactive book picker with `ipywidgets`
- Limit max number of stores per order (e.g. max 2)
- Add per-store summary stats or rankings

---

## 👥 Authors

- **Marianna Kolinko**
- **Zoriana Szumada**
- **Janek Zdaniewicz**
- **Alicja Ciurlej**

**Educational Data Analysis Project**  
Created for practical learning in price comparison, data processing, optimization, and automation.

License: MIT
