
# Axiom Sheets – Lightweight Spreadsheet

![Axiom Sheets Logo](https://images.unsplash.com/photo-1554224155-6726b3ff858f?w=1200&auto=format&fit=crop)

**Axiom Sheets** is a fully functional, browser-based spreadsheet application built with vanilla HTML, CSS, and JavaScript. It offers a smooth, responsive grid engine, formula parsing, dependency tracking, and a host of everyday spreadsheet features – all in a single `index.html` file with zero dependencies.

Whether you need to crunch numbers, organise data, or prototype formulas, Axiom Sheets provides a clean, intuitive interface that works instantly in any modern browser.

---

## ✨ Features

### 📊 High‑Performance Grid Engine
- **Virtualized rendering** – Only visible cells are rendered, allowing thousands of rows and columns without lag.
- **Smooth scrolling** – Optimised scroll handling with `requestAnimationFrame` keeps the interface fluid.
- **Column resizing** – Drag the right edge of any column header to adjust its width.

### 🧮 Formula Parser & Evaluator
- Custom **lexer** and **parser** (recursive descent) interpret formulas entered with a leading `=`.
- Supports arithmetic (`+`, `-`, `*`, `/`, `^`), comparisons (`=`, `<>`, `<`, `<=`, `>`, `>=`), string concatenation (`&`), and cell references (`A1`, `B5`).
- Range notation (`A1:B10`) and a growing library of functions:
  - `SUM`, `AVERAGE`, `MIN`, `MAX`, `COUNT`
  - `IF`, `AND`, `OR`, `NOT`
  - `CONCAT`, `ROUND`, `SQRT`, `ABS`, `UPPER`, `LOWER`

### 🔗 Dependency Graph
- A **Directed Acyclic Graph (DAG)** tracks cell dependencies.
- When a cell changes, all dependent cells recalculate instantly – no infinite loops.
- Circular references are prevented automatically.

### 🖱️ Intuitive Interaction
- **Click** to select a cell; **Shift+Click** or **drag** to select a range.
- **Double‑click** to edit a cell in place.
- **Arrow keys** to move the active cell; **Shift+Arrow** to extend selection.
- **Ctrl+C** / **Ctrl+V** to copy and paste data (including formulas).
- **Delete** / **Backspace** to clear selected cells.

### 📌 Data Tools
- **Sort A‑Z / Z‑A** – Sort the active column.
- **Filter** – Toggle filter arrows on column headers; choose which values to show.
- **Autosave** – Data is saved to `localStorage` every 500 ms, so your work survives page reloads.

### 🌓 Dark Mode
- Click the 🌙/☀️ button to switch between light and dark themes.
- Preference is stored in `localStorage`.

### 📱 Responsive Design
- The interface adapts smoothly to different screen sizes, from desktop to mobile.

---

## 🚀 Getting Started

### Option 1: Directly in the browser
1. Download or clone the repository.
2. Open `index.html` in any modern web browser (Chrome, Firefox, Edge, Safari).
3. Start typing and calculating – no server or build step required.

### Option 2: Serve locally (optional)
If you prefer to run it from a local server:
```bash
python3 -m http.server 8000
```
Then visit `http://localhost:8000`.

---

## 🖼️ Screenshots & Highlights

| | |
|:---:|:---:|
| ![Grid Overview](https://images.unsplash.com/photo-1554224155-6726b3ff858f?w=600&auto=format&fit=crop) | ![Formula Bar](https://images.unsplash.com/photo-1460925895917-afdab827c52f?w=600&auto=format&fit=crop) |
| **Virtualized Grid** – Smooth scrolling through thousands of rows | **Formula Bar** – Enter values or formulas like `=SUM(A1:B5)` |
| ![Selection & Copy](https://images.unsplash.com/photo-1554224154-26032ffc0d07?w=600&auto=format&fit=crop) | ![Dark Mode](https://images.unsplash.com/photo-1554224155-1696413565d3?w=600&auto=format&fit=crop) |
| **Drag Selection** – Select multiple cells and copy/paste | **Dark Mode** – Easy on the eyes at night |
| ![Sorting](https://images.unsplash.com/photo-1554224154-22dec7ec8818?w=600&auto=format&fit=crop) | ![Filtering](https://images.unsplash.com/photo-1554224155-6726b3ff858f?w=600&auto=format&fit=crop) |
| **Column Sorting** – Organise data instantly | **Filtering** – Show only the data you need |
| ![Formula Functions](https://images.unsplash.com/photo-1554224154-26032ffc0d07?w=600&auto=format&fit=crop) | ![Responsive](https://images.unsplash.com/photo-1554224155-1696413565d3?w=600&auto=format&fit=crop) |
| **Powerful Functions** – SUM, IF, AVERAGE and more | **Responsive Layout** – Works on mobile and tablet |

*(All images are from [Unsplash](https://unsplash.com) under the Unsplash License, free for commercial and personal use.)*

---

## 🧠 How Formulas Work

Axiom Sheets uses a custom‑built parser to interpret formulas. For example:
- `=A1+B1` – Adds the values of cells A1 and B1.
- `=IF(C3>10, "Pass", "Fail")` – Returns "Pass" if C3 > 10, otherwise "Fail".
- `=SUM(A1:A10)` – Sums all values in the range A1 to A10.
- `=AVERAGE(B2:B20)` – Calculates the average of B2:B20.

When you type a formula and press Enter, the spreadsheet:
1. **Tokenizes** the input (removing the leading `=`).
2. **Parses** the tokens into an Abstract Syntax Tree (AST).
3. **Evaluates** the AST, pulling values from referenced cells.
4. **Updates** the dependency graph so future changes propagate automatically.

If an error occurs (e.g., invalid reference or unknown function), the cell displays `#ERROR`.

---

## 📦 Project Structure

```
axiom-sheets/
├── index.html          # Main application (all HTML, CSS, JS in one file)
├── README.md           # This file
└── .gitattributes      # Git settings for line endings and language detection
```

There are no other files or dependencies – everything is self‑contained.

---

## 🛠️ Browser Support

| Browser | Support |
|--------|---------|
| Chrome |  ✅ |
| Firefox | ✅ |
| Edge |    ✅ |
| Safari |  ✅ |
| Opera |   ✅ |

Modern browsers with ES6+ support are required.

---

## 📝 License

This project is licensed under the **MIT License**. You are free to use, modify, and distribute it in any project, personal or commercial.

---

##  Acknowledgements

- Font: [Inter](https://fonts.google.com/specimen/Inter) from Google Fonts.
- Icons & emojis used for UI elements.
- Open‑source images from [Unsplash](https://unsplash.com).

---

**Happy calculating!**  
If you encounter any bugs or have feature requests, feel free to contribute or open an issue.




