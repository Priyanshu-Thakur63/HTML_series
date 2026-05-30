# HTML Tables

**Tags:** #html #web-development #tables #gfg  
**Related:** [[HTML Basics]] | [[HTML Attributes]] | [[CSS Basics]] | [[HTML Forms]]

---

## What is an HTML Table?

An HTML table organizes data into a **grid of rows and columns** — like a spreadsheet inside a webpage.

- Used to display structured data (user lists, schedules, pricing, comparison charts)
- Built using a combination of several tags working together
- Tables should be used **only for tabular data** — not for page layout (use CSS Flexbox/Grid for layout)

> **Real-world use:** Think of an HTML table like an Excel spreadsheet embedded in a webpage — rows, columns, headers, and data cells.

---

## Basic Table Structure

### Core Tags

| Tag | Full Name | Purpose |
|---|---|---|
| `<table>` | Table | Wrapper — defines the entire table |
| `<tr>` | Table Row | Creates one horizontal row |
| `<th>` | Table Header | Header cell — **bold + centered** by default |
| `<td>` | Table Data | Regular data cell |

### Syntax

```html
<table>
  <tr>
    <th>Column Header 1</th>
    <th>Column Header 2</th>
  </tr>
  <tr>
    <td>Data 1</td>
    <td>Data 2</td>
  </tr>
</table>
```

### Full Basic Example

```html
<!DOCTYPE html>
<html>
  <body>
    <table>
      <tr>
        <th>Firstname</th>
        <th>Lastname</th>
        <th>Age</th>
      </tr>
      <tr>
        <td>Priya</td>
        <td>Sharma</td>
        <td>24</td>
      </tr>
      <tr>
        <td>Arun</td>
        <td>Singh</td>
        <td>32</td>
      </tr>
      <tr>
        <td>Sam</td>
        <td>Watson</td>
        <td>41</td>
      </tr>
    </table>
  </body>
</html>
```

**Output:** A table with 1 header row + 3 data rows, 3 columns each.  
**Note:** Without CSS, the table renders with no visible borders — just text in a grid.

---

## All HTML Table Tags (Complete Reference)

| Tag | Description |
|---|---|
| `<table>` | Defines the entire table |
| `<tr>` | Defines a table row |
| `<th>` | Header cell — bold and centered by default |
| `<td>` | Standard data cell |
| `<caption>` | Title/description for the whole table — appears above it |
| `<thead>` | Groups the header rows — semantic wrapper |
| `<tbody>` | Groups the body/data rows — semantic wrapper |
| `<tfoot>` | Groups the footer rows (totals, summaries) — semantic wrapper |
| `<col>` | Applies styling to a specific column |
| `<colgroup>` | Groups columns to apply shared formatting |

<details>
<summary>Why use <code>&lt;thead&gt;</code>, <code>&lt;tbody&gt;</code>, <code>&lt;tfoot&gt;</code>?</summary>

These are **semantic grouping tags** — they don't change the visual look by default, but:
- Help browsers render large tables faster (can scroll `tbody` independently)
- Improve accessibility for screen readers
- Make CSS targeting easier (e.g., style `thead` differently from `tbody`)
- Required for professional/production-level tables

```html
<table>
  <thead>
    <tr>
      <th>Name</th>
      <th>Score</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>Alice</td>
      <td>95</td>
    </tr>
  </tbody>
  <tfoot>
    <tr>
      <td>Average</td>
      <td>95</td>
    </tr>
  </tfoot>
</table>
```

</details>

---

## Styling HTML Tables with CSS

By default, tables have no borders and look plain. CSS is used to make them look professional.

### 1. Adding a Border

```css
table, th, td {
  border: 1px solid black;
}
```

- Applies a 1px solid black border to the table, all headers, and all data cells
- Without this, the table is borderless

---

### 2. Collapsed Borders

```css
table, th, td {
  border: 1px solid black;
  border-collapse: collapse;
}
```

**Without `border-collapse`:** Each cell has its own border → double borders appear between cells  
**With `border-collapse: collapse`:** Adjacent borders merge into one clean single line

> Always use `border-collapse: collapse` for clean-looking tables.

---

### 3. Cell Padding

```css
th, td {
  padding: 20px;
}
```

- **Padding** = space between the cell's content and its border
- Without padding, text sits right against the border edges — very hard to read
- Typical values: `8px`, `12px`, `16px`, `20px`

---

### 4. Left-Align Headers

```css
th {
  text-align: left;
}
```

- By default, `<th>` text is **bold and center-aligned**
- Use `text-align: left` to align headers the same way as data cells
- Makes tables feel less "spreadsheet-like" and more readable

---

### 5. Border Spacing

```css
table {
  border-spacing: 5px;
}
```

- **Border spacing** = space *between* cells (not between content and border)
- Only works when `border-collapse` is **not** set (borders must be separate)
- Think of it as the "gap" between individual cell boxes

| Property | What it controls |
|---|---|
| `padding` | Space **inside** the cell (content → border) |
| `border-spacing` | Space **between** cells (border → border) |

---

### 6. Background Color

```css
table {
  background-color: #f2f2d1;
}
```

- Can be applied to the whole `<table>`, individual `<tr>`, `<th>`, or `<td>`
- Use an `id` to target a specific table:

```css
table#t01 {
  background-color: #f2f2d1;
}
```

```html
<table id="t01"> ... </table>
```

---

### Complete CSS Styling Example

```html
<!DOCTYPE html>
<html>
  <head>
    <style>
      table, th, td {
        border: 1px solid black;
        border-collapse: collapse;
      }
      th, td {
        padding: 12px;
        text-align: left;
      }
      th {
        background-color: #4CAF50;
        color: white;
      }
      tr:nth-child(even) {
        background-color: #f2f2f2;
      }
    </style>
  </head>
  <body>
    <table style="width: 100%">
      <tr>
        <th>Firstname</th>
        <th>Lastname</th>
        <th>Age</th>
      </tr>
      <tr>
        <td>Priya</td>
        <td>Sharma</td>
        <td>24</td>
      </tr>
      <tr>
        <td>Arun</td>
        <td>Singh</td>
        <td>32</td>
      </tr>
    </table>
  </body>
</html>
```

> `tr:nth-child(even)` gives alternating row colors — a very common pattern called a **zebra stripe table**.

---

## Spanning Columns and Rows

### `colspan` — Merge Cells Horizontally

Makes one cell spread across **multiple columns**.

```html
<tr>
  <th>Name</th>
  <th colspan="2">Telephone</th>  <!-- spans 2 columns -->
</tr>
<tr>
  <td>Vikas Rawat</td>
  <td>9125577854</td>
  <td>8565557785</td>
</tr>
```

**Output:** "Telephone" header sits above both phone number columns.

---

### `rowspan` — Merge Cells Vertically

Makes one cell spread across **multiple rows**.

```html
<tr>
  <th>Name:</th>
  <td>Vikas Rawat</td>
</tr>
<tr>
  <th rowspan="2">Telephone:</th>  <!-- spans 2 rows -->
  <td>9125577854</td>
</tr>
<tr>
  <td>8565557785</td>
</tr>
```

**Output:** "Telephone:" label sits beside both phone numbers vertically.

| Attribute | Direction | Effect |
|---|---|---|
| `colspan="2"` | Horizontal → | Cell spans 2 columns |
| `rowspan="2"` | Vertical ↓ | Cell spans 2 rows |

---

## Adding a Table Caption

The `<caption>` tag adds a **title above the table**. Place it immediately after the opening `<table>` tag.

```html
<table style="width: 100%">
  <caption>Employee Details</caption>
  <tr>
    <th>Firstname</th>
    <th>Lastname</th>
    <th>Age</th>
  </tr>
  <tr>
    <td>Priya</td>
    <td>Sharma</td>
    <td>24</td>
  </tr>
</table>
```

**Output:** "Employee Details" appears centered above the table.

> Good for accessibility — screen readers announce the caption before reading table content.

---

## Nested Tables

A table can contain another table inside a `<td>` cell.

```html
<table border="1">
  <tr>
    <td>Outer Table - Column 1</td>
    <td>
      <!-- Inner table inside a cell -->
      <table border="1">
        <tr><td>Inner Row 1</td></tr>
        <tr><td>Inner Row 2</td></tr>
      </table>
    </td>
  </tr>
</table>
```

> ⚠️ **Avoid nesting tables unnecessarily.** They make HTML hard to read and maintain. Use CSS for complex layouts instead.

---

## Best Practices

✅ Always use `<thead>`, `<tbody>`, `<tfoot>` for structured tables  
✅ Always add `border-collapse: collapse` when adding borders  
✅ Always add `padding` to cells for readability  
✅ Use `<caption>` to label tables — helps accessibility  
✅ Use `colspan`/`rowspan` for merging cells logically  
✅ Set `width: 100%` on `<table>` for full-width responsive tables  

❌ **Never use tables for page layout** — use CSS Flexbox or Grid instead  
❌ Don't nest tables deeply — it creates maintenance nightmares  
❌ Don't skip semantic grouping tags (`thead`/`tbody`) in production code  
❌ Don't use the deprecated `border` attribute directly on `<table>` — use CSS  

---

## Common Beginner Mistakes

- **Forgetting `<tr>` around cells** — `<td>` must always be inside a `<tr>`
- **Mismatched `colspan`/`rowspan` counts** — cells disappear or overlap if counts don't add up
- **Using tables for layout** — a very old practice; modern HTML uses CSS Grid/Flexbox for layout
- **No padding on cells** — text looks cramped without padding
- **Missing `border-collapse`** — double borders appear between cells
- **Putting `<caption>` after rows** — `<caption>` must be the **first child** of `<table>`

---

## Interview / Important Notes

- `<th>` = header cell → **bold + centered** by default; `<td>` = data cell → normal weight + left-aligned
- `colspan` merges **columns** (horizontal); `rowspan` merges **rows** (vertical)
- `border-collapse: collapse` removes double borders between adjacent cells
- `padding` = space inside a cell; `border-spacing` = space between cells
- `<caption>` must come **immediately after** `<table>` opening tag
- `<thead>`, `<tbody>`, `<tfoot>` are semantic — they don't visually change the table unless CSS targets them
- Tables should **only** be used for tabular data, not page layout

---

## Mini Practice

Build this table from scratch:

**Goal:** A course schedule table with merged cells

```html
<!DOCTYPE html>
<html>
  <head>
    <style>
      table, th, td {
        border: 1px solid #333;
        border-collapse: collapse;
      }
      th, td {
        padding: 10px;
        text-align: left;
      }
      th {
        background-color: #333;
        color: white;
      }
    </style>
  </head>
  <body>
    <table style="width: 100%">
      <caption>Weekly Class Schedule</caption>
      <thead>
        <tr>
          <th>Day</th>
          <th colspan="2">Subjects</th>
        </tr>
      </thead>
      <tbody>
        <tr>
          <td rowspan="2">Monday</td>
          <td>HTML Basics</td>
        </tr>
        <tr>
          <td>CSS Fundamentals</td>
        </tr>
        <tr>
          <td>Tuesday</td>
          <td colspan="2">JavaScript</td>
        </tr>
      </tbody>
    </table>
  </body>
</html>
```

**Challenge:** Add a `<tfoot>` row showing "Total: 3 classes" using `colspan` to span all columns.

---
