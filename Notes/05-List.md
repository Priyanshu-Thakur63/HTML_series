# HTML Lists

**Tags:** #html #web-development #lists #gfg  
**Related:** [[HTML Basics]] | [[HTML Tables]] | [[CSS Basics]]

---

## What are HTML Lists?

HTML lists organize content into a structured, readable format — either in a specific order or as a simple collection of items.

- Built using `<ul>`, `<ol>`, `<dl>`, and `<li>` tags
- Make content easier to scan and understand
- Used everywhere: navigation menus, step-by-step instructions, glossaries, feature lists

> **Real-world use:** Every navigation bar, FAQ section, recipe, and step-by-step tutorial on the web uses HTML lists under the hood.

---

## Types of HTML Lists

There are **3 types** of lists in HTML:

| Type | Tag | Use Case | Default Marker |
|---|---|---|---|
| Unordered List | `<ul>` | Items with no specific order | Bullet point `•` |
| Ordered List | `<ol>` | Items that follow a sequence | Numbers `1, 2, 3` |
| Description List | `<dl>` | Term + definition pairs | None |

---

## 1. Unordered List — `<ul>`

Used when the **order of items doesn't matter** — like a grocery list or a list of features.

- Wrapped in `<ul>` tag
- Each item uses `<li>` tag
- Items display with a **bullet point** by default

### Syntax

```html
<ul>
  <li>Item 1</li>
  <li>Item 2</li>
  <li>Item 3</li>
</ul>
```

### Example

```html
<h2>Grocery List</h2>
<ul>
  <li>Bread</li>
  <li>Eggs</li>
  <li>Milk</li>
  <li>Coffee</li>
</ul>
```

**Output:**
- Bread
- Eggs
- Milk
- Coffee

### `<ul>` Attributes

| Attribute | Description | Note |
|---|---|---|
| `type` | Changes the bullet style | Use CSS `list-style-type` instead in modern HTML |
| `compact` | Renders list smaller | Deprecated — use CSS |

### Changing Bullet Style with CSS

```css
/* Common list-style-type values */
ul { list-style-type: disc; }      /* • default */
ul { list-style-type: circle; }    /* ○ hollow circle */
ul { list-style-type: square; }    /* ■ filled square */
ul { list-style-type: none; }      /* no bullet — used for nav menus */
```

---

## 2. Ordered List — `<ol>`

Used when the **sequence matters** — like steps in a tutorial, rankings, or instructions.

- Wrapped in `<ol>` tag
- Each item uses `<li>` tag
- Items are **numbered by default** starting from 1

### Syntax

```html
<ol>
  <li>Item 1</li>
  <li>Item 2</li>
  <li>Item 3</li>
</ol>
```

### Example

```html
<h3>Steps to Make Tea</h3>
<ol>
  <li>Boil water</li>
  <li>Add tea leaves</li>
  <li>Pour into cup</li>
  <li>Add milk and sugar</li>
</ol>
```

**Output:**
1. Boil water
2. Add tea leaves
3. Pour into cup
4. Add milk and sugar

### `<ol>` Attributes

| Attribute | Value | Description | Example Output |
|---|---|---|---|
| `type` | `1` | Numbers (default) | 1, 2, 3 |
| `type` | `A` | Uppercase letters | A, B, C |
| `type` | `a` | Lowercase letters | a, b, c |
| `type` | `I` | Uppercase Roman numerals | I, II, III |
| `type` | `i` | Lowercase Roman numerals | i, ii, iii |
| `start` | any number | Starting number/letter | `start="5"` → 5, 6, 7 |
| `reversed` | — | Counts down instead of up | 3, 2, 1 |

### Attribute Examples

```html
<!-- Reversed list: counts down -->
<ol reversed>
  <li>HTML</li>
  <li>CSS</li>
  <li>JS</li>
</ol>
<!-- Output: 3, 2, 1 -->

<!-- Start from 5 -->
<ol start="5">
  <li>HTML</li>
  <li>CSS</li>
  <li>JS</li>
</ol>
<!-- Output: 5, 6, 7 -->

<!-- Roman numerals -->
<ol type="i">
  <li>HTML</li>
  <li>CSS</li>
  <li>JS</li>
</ol>
<!-- Output: i, ii, iii -->
```

---

## 3. Description List — `<dl>`

Used for **term + definition pairs** — like a glossary, dictionary, FAQ, or key-value data.

- `<dl>` — wraps the entire description list
- `<dt>` — **Description Term** (the word/title being defined)
- `<dd>` — **Description Details** (the definition/explanation, indented by default)

### Syntax

```html
<dl>
  <dt>Term 1</dt>
  <dd>Definition of Term 1</dd>
  <dt>Term 2</dt>
  <dd>Definition of Term 2</dd>
</dl>
```

### Example

```html
<h2>Shopping List with Quantities</h2>
<dl>
  <dt>Coffee</dt>
  <dd>500 gms</dd>
  <dt>Milk</dt>
  <dd>1 litre Tetra Pack</dd>
</dl>
```

**Output:**  
**Coffee**  
&nbsp;&nbsp;&nbsp;&nbsp;500 gms  
**Milk**  
&nbsp;&nbsp;&nbsp;&nbsp;1 litre Tetra Pack

### Real-World Use Cases for `<dl>`

```html
<!-- Glossary -->
<dl>
  <dt>HTML</dt>
  <dd>HyperText Markup Language — used to structure web pages</dd>

  <dt>CSS</dt>
  <dd>Cascading Style Sheets — used to style web pages</dd>
</dl>

<!-- FAQ -->
<dl>
  <dt>What is a browser?</dt>
  <dd>A browser is software used to access the internet (e.g. Chrome, Firefox).</dd>
</dl>
```

---

## Nested Lists

Any list type can be nested inside another — just place a new `<ul>` or `<ol>` inside an `<li>`.

```html
<ul>
  <li>Frontend
    <ul>
      <li>HTML</li>
      <li>CSS</li>
      <li>JavaScript</li>
    </ul>
  </li>
  <li>Backend
    <ul>
      <li>Node.js</li>
      <li>Python</li>
    </ul>
  </li>
</ul>
```

**Output:**
- Frontend
  - HTML
  - CSS
  - JavaScript
- Backend
  - Node.js
  - Python

> **Tip:** Browsers automatically indent nested lists and change bullet styles for each level.

---

## Combined Example (Ordered + Unordered)

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <title>HTML Lists</title>
  </head>
  <body>
    <h2>Welcome To GeeksforGeeks Learning</h2>

    <h5>Available Courses</h5>
    <ul>
      <li>Data Structures & Algorithms</li>
      <li>Web Technology</li>
      <li>Aptitude & Logical Reasoning</li>
      <li>Programming Languages</li>
    </ul>

    <h5>Data Structures Topics (in order)</h5>
    <ol>
      <li>Array</li>
      <li>Linked List</li>
      <li>Stacks</li>
      <li>Queues</li>
      <li>Trees</li>
      <li>Graphs</li>
    </ol>
  </body>
</html>
```

---

## Quick Comparison — All 3 List Types

| Feature | `<ul>` | `<ol>` | `<dl>` |
|---|---|---|---|
| Default marker | Bullet `•` | Numbers `1, 2, 3` | None |
| Order matters? | ❌ No | ✅ Yes | ❌ No |
| Item tag | `<li>` | `<li>` | `<dt>` + `<dd>` |
| Best for | Feature lists, nav menus | Steps, rankings, instructions | Glossaries, FAQs, definitions |
| Can be nested? | ✅ Yes | ✅ Yes | ✅ Yes |

---

## Best Practices

✅ Use `<ul>` for navigation menus (with `list-style: none` in CSS)  
✅ Use `<ol>` whenever sequence matters — tutorials, recipes, steps  
✅ Use `<dl>` for glossaries, FAQs, or any term-definition content  
✅ Nest lists to show hierarchy — but keep it to **2-3 levels max**  
✅ Use CSS `list-style-type` instead of the deprecated `type` attribute on `<ul>`  

❌ Don't use `<br>` to fake a list — use proper list tags  
❌ Don't nest too deeply — more than 3 levels becomes hard to read  
❌ Don't use the `compact` attribute — it's deprecated; use CSS instead  
❌ Don't use ordered lists when order doesn't actually matter  

---

## Common Beginner Mistakes

- **Forgetting `<li>` tags** — placing text directly inside `<ul>`/`<ol>` without `<li>` is invalid HTML
- **Confusing `<ul>` and `<ol>`** — use `<ol>` only when the sequence genuinely matters
- **Not knowing `<dl>` exists** — many beginners only know `<ul>` and `<ol>`; `<dl>` is great for definitions and FAQs
- **Using `type` attribute on `<ul>`** — deprecated; change bullet style with CSS `list-style-type` instead
- **Breaking nesting structure** — the nested list must go **inside** the `<li>`, not after it

---

## Interview / Important Notes

- There are **3 types** of HTML lists: unordered (`<ul>`), ordered (`<ol>`), description (`<dl>`)
- `<li>` is used for items in both `<ul>` and `<ol>`
- `<dl>` uses `<dt>` (term) and `<dd>` (definition) — no `<li>`
- `<ol>` attributes: `type`, `start`, `reversed`
- `type` values for `<ol>`: `1`, `A`, `a`, `I`, `i`
- `reversed` attribute makes the list count down (no value needed — it's a boolean attribute)
- `list-style-type: none` in CSS removes bullets — used for nav menus
- The `compact` attribute is **deprecated** in HTML5

---

## Mini Practice

Build this page using all three list types:

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <title>My Learning Plan</title>
  </head>
  <body>

    <!-- Unordered list -->
    <h2>Topics to Learn</h2>
    <ul>
      <li>HTML</li>
      <li>CSS</li>
      <li>JavaScript</li>
    </ul>

    <!-- Ordered list with type and start -->
    <h2>Learning Steps</h2>
    <ol type="A" start="1">
      <li>Watch the video</li>
      <li>Read the notes</li>
      <li>Practice with code</li>
      <li>Build a mini project</li>
    </ol>

    <!-- Description list -->
    <h2>Key Terms</h2>
    <dl>
      <dt>HTML</dt>
      <dd>Structures the content of a webpage</dd>
      <dt>CSS</dt>
      <dd>Styles the visual appearance of a webpage</dd>
      <dt>JavaScript</dt>
      <dd>Adds interactivity and logic to a webpage</dd>
    </dl>

  </body>
</html>
```

**Challenge:** Add a nested `<ul>` inside the "JavaScript" `<li>` of the first list, with sub-items: Variables, Functions, DOM.