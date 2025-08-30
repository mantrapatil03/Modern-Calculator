
# Modern Calculator

A sleek, responsive calculator built with **HTML**, **Tailwind CSS**, and **vanilla JavaScript**. Includes calculation **history**, **keyboard support**, **light/dark theme toggle**, and smooth button animations. All data (history + theme) persist locally via `localStorage`.

---

## ✨ Features

* **Responsive UI** with Tailwind and rounded cards/shadows
* **History panel** with timestamped entries (click to reuse results)
* **Keyboard support** (numbers, operators, Enter, %, Backspace, Esc)
* **Light/Dark theme toggle** (persisted)
* **Safe-ish evaluation** with basic parentheses validation
* **Local persistence** of history (up to 10 recent calculations)

---

## 🧱 Tech Stack

* **HTML5** – single-page app
* **Tailwind CSS** (via CDN)
* **Vanilla JavaScript** (no frameworks)
* **localStorage** – persistence

---

## 🚀 Getting Started

### Prerequisites

No build tools required. You just need a modern browser.

### Run Locally

1. Clone or download this repo.
2. Open `index.html` in your browser.

> Tip: If you use a strict browser setting that blocks `file://` access to `localStorage`, run a tiny local server:

```bash
# Python 3
python -m http.server 5500
# then open http://localhost:5500/index.html
```

---

## 🕹️ Usage

### Buttons

* **AC** – clear display & current expression
* **← (Backspace)** – delete last character
* **+/-** – toggle sign of the current number
* **%** – convert current value to percentage (÷100)
* **( )** – parentheses
* **÷ × − +** – operators
* **=** – evaluate
* **History** – toggle the history panel

### Keyboard Shortcuts

* **Digits & operators**: `0–9`, `+ - * / ( ) .`
* **Enter / =**: evaluate
* **%**: percentage
* **Backspace**: delete last character
* **Esc**: clear all

### History

* Stores the **last 10** calculations.
* Click a history row to **reuse the result** in the display.
* **Clear All** to wipe history.

### Theme

* Click the **sun/moon** icon to toggle **light/dark**.
* Preference is saved in `localStorage` under `darkMode`.

---

## 🔒 Security Notes

This app evaluates arithmetic expressions using:

```js
const fn = new Function(`return ${expr}`);
return fn();
```

To reduce risk, a **basic validation** is performed (parentheses balancing). For production-grade safety, consider:

* Using a **proper math parser** (e.g., math.js) instead of `new Function()`.
* Implementing a token-based parser supporting only numbers/operators/parentheses.

---

## 🗂️ Project Structure

```
index.html  # All HTML, CSS (inline), and JS (inline)
```

---

## ⚙️ Customization

* **History size**: change the `10` limit in `saveToHistory`.
* **Rounding**: results rounded to **10 decimal places**; adjust in `calculate()`.
* **Tailwind theme**: tweak colors, spacing, and typography in classes.
* **Dark mode logic**: controlled by `isDarkMode` + `updateTheme()`.

---

## 🧪 Known Limitations

* **Input validation** is minimal (balanced parentheses only).
* **Decimal handling** prevents multiple `.` in the entire display, not per-number segment.
* Unary `-` works via **+/-** toggle; parsing of complex unary expressions is simplistic.

---

## 🛣️ Roadmap / Ideas

* Replace `new Function()` with a **safe expression parser**
* Support **scientific functions** (√, x², 1/x, sin, cos, tan)
* Allow **multiple decimals** per number segment (context-aware)
* **Intl formatting** (thousands separators)
* **PWA** support for offline install
* **Unit tests** for evaluation & edge cases
* **Haptic feedback** on mobile

---

## 🐞 Troubleshooting

* **Nothing saves**: ensure your browser allows `localStorage` for the page origin.
* **Keyboard not working**: some inputs may intercept keys; click once on the page to focus.
* **Theme not persisting**: check `localStorage['darkMode']` in DevTools.

---



---

## 🙏 Credits

* Icons: **Heroicons** (via SVG)
* Styling: **Tailwind CSS** CDN

---

## 📷 Screenshots (optional)

<img width="463" height="485" alt="image" src="https://github.com/user-attachments/assets/2d0a1886-94c4-46ce-8ecd-7138a3fa249b" />


## 👨‍💻 Author

Mantra Patil
