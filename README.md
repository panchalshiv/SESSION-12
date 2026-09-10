[README.md](https://github.com/user-attachments/files/32073345/README.md)
# Session 12 — Lambda, Map, Filter & Reduce in Python

This notebook contains a set of small exercises demonstrating Python's
`lambda` expressions together with the built-in functional tools `map()`,
`filter()`, and `functools.reduce()`.

## Contents

### 1. GST Price Calculator
Calculates the final price of a product after adding 18% GST using a `lambda` function.

```python
gst_price = lambda price: price + (price * 0.18)

print("Price 100:", gst_price(100))
print("Price 250:", gst_price(250))
print("Price 500:", gst_price(500))
```

**Output:**
```
Price 100: 118.0
Price 250: 295.0
Price 500: 590.0
```

---

### 2. Cleaning Song Titles with `map()`
Strips extra whitespace and converts each song title to title case.

```python
songs = [' shape OF you ', ' believer', 'KESARIYA ', ' blinding LIGHTS']

cleaned_songs = list(map(lambda song: song.strip().title(), songs))

print(cleaned_songs)
```

**Output:**
```
['Shape Of You', 'Believer', 'Kesariya', 'Blinding Lights']
```

---

### 3. Filtering Products Starting with "S"
Uses `filter()` to select product names that start with the letter "S" (case-insensitive).

```python
products = ["Shoes", "Laptop", "Smartphone", "Watch", "Shirt", "Camera"]

s_products = list(filter(lambda product: product.lower().startswith("s"), products))

print(s_products)
```

**Output:**
```
['Shoes', 'Smartphone', 'Shirt']
```

---

### 4. Total Bill Amount with `reduce()`
Sums up a list of order amounts using `functools.reduce()`.

```python
from functools import reduce

order_amounts = [120, 340, 560, 80]

total = reduce(lambda x, y: x + y, order_amounts)

print("Total bill amount:", total)
```

**Output:**
```
Total bill amount: 1100
```

---

### 5. Combined Pipeline — `map()` → `filter()` → `reduce()`
Doubles each number, keeps values greater than 100, then sums the remaining values — chaining all three functional tools together.

```python
from functools import reduce

numbers = [40, 60, 80, 120]

# Step 1: Double each number
doubled = list(map(lambda x: x * 2, numbers))

# Step 2: Keep numbers greater than 100
filtered = list(filter(lambda x: x > 100, doubled))

# Step 3: Calculate the total
total = reduce(lambda x, y: x + y, filtered)

print("Doubled:", doubled)
print("Filtered:", filtered)
print("Total:", total)
```

**Output:**
```
Doubled: [80, 120, 160, 240]
Filtered: [120, 160, 240]
Total: 520
```

---

## Requirements
- Python 3.x
- No external libraries needed (`functools` is part of the standard library)

## How to Run
Open `session_12.ipynb` in Jupyter Notebook / JupyterLab and run the cells sequentially, or run the equivalent `.py` scripts from the command line.
