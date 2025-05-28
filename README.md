project: "📚 Book Purchase Profitability Analysis"

description: >
  This project compares two strategies for purchasing school books across multiple bookstores:
    1️⃣ Buy the entire wishlist from a single bookstore (one shipping fee)
    2️⃣ Buy each book from the cheapest available bookstore (multiple shipping fees)
  
  The analysis takes into account various promotions offered by bookstores such as:
    - Free shipping thresholds
    - Percentage discounts
    - "3 for 2" or "Buy 1 get 1 free" deals

structure:
  - path: "Data/Lektury_szkolne_baza.xlsx"
    description: "List of books with individual prices and shipping costs per bookstore"
  - path: "Data/promocje_księgarnie.xlsx"
    description: "Bookstore promotions with corresponding Python-formatted discount logic"
  - path: "Notebooks/Project.ipynb"
    description: "Main Jupyter Notebook containing the code, test cases, and analysis"
  - path: "README.yaml"
    description: "This documentation file"

data_inputs:
  books:
    file: "Data/Lektury_szkolne_baza.xlsx"
    columns:
      - id księgarni
      - nazwa książki
      - cena książki
      - cena dostawy
  promotions:
    file: "Data/promocje_księgarnie.xlsx"
    columns:
      - id_księgarni
      - promotion_name
      - formula  # Python expression applied to prices/shipping

usage:
  instructions:
    - "Open 'Notebooks/Project.ipynb' in Jupyter"
    - "Ensure both Excel files are available in the 'Data/' folder"
    - "Execute cells in order: data loading, cleaning, function setup, test cases, and final plots"
    - "To test different scenarios, update the 'wishlist' list in the test case cells"

test_cases:
  - name: "Test 1 – School Basics"
    wishlist:
      - "Opowieści z Narnii: Lew, czarownica i stara szafa"
      - "W pustyni i w puszczy"
      - "Akademia pana Kleksa"
      - "Chłopcy z Placu Broni"

  - name: "Test 2 – Extended Set"
    wishlist:
      - "Mały Książę"
      - "Balladyna"
      - "Pan Tadeusz"
      - "Latarnik"

  - name: "Test 3 – Full Class Set"
    wishlist:
      - "Syzyfowe prace"
      - "Zemsta"
      - "Katarynka"
      - "Kamienie na szaniec"

  - name: "Test 4 – Minimal Basket"
    wishlist:
      - "Balladyna"
      - "Latarnik"

  - name: "Test 5 – Max Value Basket"
    wishlist:
      - "Opowieści z Narnii: Lew, czarownica i stara szafa"
      - "Pan Tadeusz"
      - "Akademia pana Kleksa"
      - "Zemsta"
      - "Syzyfowe prace"

visualization:
  type: "📊 Bar Chart"
  description: >
    The final chart displays a comparison of total purchase costs between:
      - One-bookstore strategy (with all books in a single shop)
      - Split-by-book strategy (picking each book from the cheapest source)

technologies:
  - Python 3.12+
  - Jupyter Notebook
  - Pandas
  - Matplotlib

extensions:
  - "Export final comparison to Excel/CSV"
  - "Add interactive wishlist using ipywidgets"
  - "Detect bookstores that offer the complete wishlist"
  - "Visual analysis of promotion impact"

author: "📘 Educational Data Analysis Project"
license: "MIT"
