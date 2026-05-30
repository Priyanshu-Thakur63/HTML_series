# Project — Simple Online Survey System

**Tags:** #html #web-development #project #forms #tables #lists #gfg  
**Related:** [[HTML Forms]] | [[HTML Tables]] | [[HTML Lists]] | [[HTML Basics]]

---

## Project Overview

This is a beginner HTML project that combines everything learned so far — forms, tables, lists, and comments — into one working webpage.

**What it builds:** A customer feedback survey page with:
- A form to collect user responses
- An instructions list to guide the user
- A table to display submitted responses

> **Key learning:** This project shows how individual HTML concepts work **together** as a complete webpage — a critical skill for real-world development.

---

## Concepts Used in This Project

| Concept | Tags Used | Purpose |
|---|---|---|
| Page structure | `<!DOCTYPE>`, `<html>`, `<head>`, `<body>` | Foundation of the page |
| Form | `<form>`, `<input>`, `<select>`, `<textarea>` | Collect user input |
| Lists | `<ul>`, `<li>` | Display survey instructions |
| Tables | `<table>`, `<tr>`, `<th>`, `<td>` | Display survey responses |
| Comments | `<!-- -->` | Document each section of code |

---

## Building It Step by Step

### Step 1 — Basic HTML Structure

Always start with the boilerplate before adding content.

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Online Survey</title>
  </head>
  <body>
    <h1>Customer Feedback Survey</h1>
    <p>Please take a moment to complete the survey below.</p>
  </body>
</html>
```

**What's happening:**
- `<!DOCTYPE html>` — triggers Standards Mode
- `<meta charset="UTF-8">` — supports all characters and symbols
- `<meta name="viewport">` — makes the page mobile-friendly
- `<title>` — shows "Online Survey" in the browser tab
- `<h1>` — main heading visible on the page
- `<p>` — short description below the heading

---

### Step 2 — Create the Survey Form

Add a `<form>` with input fields for name, age, a dropdown for colour, and a textarea for feedback.

```html
<!-- Form to collect survey responses -->
<form action="#" method="post">

  <!-- User Name Field -->
  <label for="name">Your Name:</label>
  <input type="text" id="name" name="name" required><br><br>

  <!-- Age Input Field -->
  <label for="age">Your Age:</label>
  <input type="number" id="age" name="age" required><br><br>

  <!-- Dropdown for Favorite Color -->
  <label for="color">Favorite Color:</label>
  <select id="color" name="color">
    <option value="red">Red</option>
    <option value="blue">Blue</option>
    <option value="green">Green</option>
    <option value="yellow">Yellow</option>
  </select><br><br>

  <!-- Feedback Text Area -->
  <label for="feedback">Your Feedback:</label><br>
  <textarea id="feedback" name="feedback" rows="4" cols="50" required></textarea><br><br>

  <!-- Submit Button -->
  <input type="submit" value="Submit">

</form>
```

**Field-by-field breakdown:**

| Field | Tag Used | Type | Why |
|---|---|---|---|
| Name | `<input>` | `type="text"` | Free text, single line |
| Age | `<input>` | `type="number"` | Numeric only, browser validates |
| Favourite Color | `<select>` + `<option>` | Dropdown | Restricts to predefined choices |
| Feedback | `<textarea>` | — | Multi-line free text |
| Submit | `<input>` | `type="submit"` | Sends the form |

> **Note on `action="#"`:** The `#` means the form submits to the same page. In a real project, this would point to a backend URL like `action="/submit-survey"`.

---

### Step 3 — Display Responses in a Table

In a real app, submitted data would come from a database via backend code. Here, we **hardcode sample responses** to simulate what results would look like.

```html
<!-- Survey Responses Table -->
<h2>Survey Responses</h2>
<table border="1">
  <tr>
    <th>Name</th>
    <th>Age</th>
    <th>Favorite Color</th>
    <th>Feedback</th>
  </tr>
  <tr>
    <td>Alice</td>
    <td>30</td>
    <td>Blue</td>
    <td>Great service! Keep it up.</td>
  </tr>
  <tr>
    <td>Bob</td>
    <td>25</td>
    <td>Green</td>
    <td>Would love to see more options.</td>
  </tr>
</table>
```

> In a real project, this table would be dynamically populated using JavaScript or a backend language like Python, PHP, or Node.js. For now, it's static HTML to practise table structure.

---

### Step 4 — Add Instructions Using a List

Use an unordered list to guide users on how to fill out the survey.

```html
<!-- Survey Instructions -->
<h3>Instructions:</h3>
<ul>
  <li>Fill in your name and age in the first two fields.</li>
  <li>Select your favorite color from the dropdown list.</li>
  <li>Provide your feedback in the text box below.</li>
  <li>Click the "Submit" button to submit your responses.</li>
</ul>
```

---

### Step 5 — Add Comments Throughout

Comments help anyone reading the code (including future-you) understand what each section does.

```html
<!-- Survey Form -->
<!-- Survey Instructions -->
<!-- Survey Responses Table -->
```

Place comments **above** each major section as section markers.

---

## Final Complete Code

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Online Survey</title>
  </head>
  <body>

    <h1>Customer Feedback Survey</h1>
    <p>Please take a moment to complete the survey below.</p>

    <!-- Survey Form -->
    <form action="#" method="post">

      <label for="name">Your Name:</label>
      <input type="text" id="name" name="name" required><br><br>

      <label for="age">Your Age:</label>
      <input type="number" id="age" name="age" required><br><br>

      <label for="color">Favorite Color:</label>
      <select id="color" name="color">
        <option value="red">Red</option>
        <option value="blue">Blue</option>
        <option value="green">Green</option>
        <option value="yellow">Yellow</option>
      </select><br><br>

      <label for="feedback">Your Feedback:</label><br>
      <textarea id="feedback" name="feedback" rows="4" cols="50" required></textarea><br><br>

      <input type="submit" value="Submit">

    </form>

    <!-- Survey Instructions -->
    <h3>Instructions:</h3>
    <ul>
      <li>Fill in your name and age in the first two fields.</li>
      <li>Select your favorite color from the dropdown list.</li>
      <li>Provide your feedback in the text box below.</li>
      <li>Click the "Submit" button to submit your responses.</li>
    </ul>

    <!-- Survey Responses Table -->
    <h2>Survey Responses</h2>
    <table border="1">
      <tr>
        <th>Name</th>
        <th>Age</th>
        <th>Favorite Color</th>
        <th>Feedback</th>
      </tr>
      <tr>
        <td>Alice</td>
        <td>30</td>
        <td>Blue</td>
        <td>Great service! Keep it up.</td>
      </tr>
      <tr>
        <td>Bob</td>
        <td>25</td>
        <td>Green</td>
        <td>Would love to see more options.</td>
      </tr>
    </table>

  </body>
</html>
```

---

## How the HTML Concepts Connect Here

```
<body>
  │
  ├── <h1> + <p>          → Page heading and intro text
  │
  ├── <form>              → Collects user input
  │     ├── <input type="text">     → Name
  │     ├── <input type="number">   → Age
  │     ├── <select> + <option>     → Favourite Color (dropdown)
  │     ├── <textarea>              → Feedback (multi-line)
  │     └── <input type="submit">   → Submit button
  │
  ├── <ul> + <li>         → Instructions list
  │
  └── <table>             → Displays survey responses
        ├── <th> row      → Column headers
        └── <td> rows     → Sample data
```

---

## What's Missing (For a Real Project)

This is a **pure HTML** project — it has limitations that would be solved in later stages of learning:

| Limitation | Solution (Learned Later) |
|---|---|
| Form data doesn't actually save | Backend (Node.js, Python, PHP) + Database |
| Table is hardcoded, not dynamic | JavaScript DOM / Backend templating |
| No styling | CSS |
| No validation beyond `required` | JavaScript form validation |
| `action="#"` does nothing useful | A real server endpoint |

> This is completely normal for an HTML-only project. The goal here is to understand **structure** — logic and data handling come later with JavaScript and backend.

---

## Best Practices Applied in This Project

✅ `<!DOCTYPE html>` declared at the top  
✅ `<meta charset>` and `<meta viewport>` included  
✅ Every `<input>` has a matching `<label>` with correct `for`/`id` pairing  
✅ `required` attribute used on mandatory fields  
✅ Comments used to label every major section  
✅ Meaningful `name` attributes on all inputs  
✅ `<select>` used instead of free text where choices are limited  

---

## Mini Challenge

Extend this project by adding these fields to the form:

1. **Rating** — radio buttons (`type="radio"`) for 1–5 stars, grouped with `name="rating"`
2. **Newsletter signup** — a checkbox (`type="checkbox"`) labelled "Subscribe to newsletter"
3. **Country** — a `<select>` dropdown with at least 5 country options
4. Add a new column to the responses table for **Rating**

> Try building it yourself first, then check by referring back to [[HTML Forms]] and [[HTML Tables]] notes.