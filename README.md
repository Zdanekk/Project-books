# 📚 Book Purchase Profitability Analysis

This project compares two purchasing strategies for school books across multiple online bookstores:

1. **Single-store purchase** – Buy all books from one bookstore (one shipping fee).
2. **Split-by-book purchase** – Buy each book from the cheapest available store (multiple shipping fees).

The logic also applies real-world bookstore promotions such as:

- Free shipping thresholds
- Percentage discounts
- "3 for 2" or bundle deals

---

## 📁 Project Structure

Folders and files:

- `Data/Lektury_szkolne_baza.xlsx` – book prices and shipping info
- `Data/promocje_księgarnie.xlsx` – discount formulas per bookstore
- `Notebooks/Project.ipynb` – main Jupyter Notebook with logic, tests, and charts
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

Contains dynamic promotion logic written in Python (to simulate discounts).

Example:

| Store ID | Promotion Name            | Formula                                      |
|----------|---------------------------|----------------------------------------------|
| 1        | Free shipping over 100 zł | `if total_price >= 100: shipping_cost = 0`   |
| 3        | 3 for 2                   | `total_price -= sum(prices[:len(prices)//3])`|

---

## ▶️ How to Run the Notebook

1. Open `Notebooks/Project.ipynb` in Jupyter Notebook.
2. Make sure both Excel files are in the `Data/` folder.
3. Run cells in order:
   - Load and clean data
   - Define promotion functions
   - Run test cases
   - View cost comparison and plots

---

## 🧪 Test Cases

The notebook includes 5 test cases, such as:

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

---

## 📈 Chart Comparison

At the end of the notebook, a bar chart visualizes the difference in total cost between:

- Buying everything from one store
- Splitting the order across cheapest options

---

## 🧰 Technologies Used

- Python 3.12+
- Jupyter Notebook
- Pandas
- Matplotlib

---

## 🚀 Possible Extensions

- Export result tables to `.xlsx` or `.csv`
- Add an interactive wishlist editor with `ipywidgets`
- Show which stores offer full sets
- Add promo effectiveness analysis per store

---

## 👥 Authors

- **Marianna Kolinko**
- **Zoriana Szumada**
- **Janek Zdaniewicz**
- **Alicja Ciurlej**


**Educational Data Analysis Project**

Created for practical learning in price comparison, data manipulation, and promotion simulation.

License: MIT
