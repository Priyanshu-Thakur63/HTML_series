# HTML Forms

**Tags:** #html #web-development #forms #gfg  
**Related:** [[HTML Basics]] | [[HTML Lists]] | [[HTML Tables]] | [[CSS Basics]] | [[JavaScript DOM]]

---

## What is an HTML Form?

An HTML form is a section of a webpage that collects **input from the user** and sends it somewhere — usually to a server or a script for processing.

- Built using the `<form>` tag and various input elements inside it
- Used for login pages, sign-up forms, search bars, checkout pages, surveys, etc.
- Over **85% of websites** use forms to gather user data

> **Real-world analogy:** A form on a webpage is like a paper form at a government office — you fill in your details, and submit it to be processed.

---

## Basic Syntax

```html
<form>
  <!-- form elements go here -->
</form>
```

---

## Basic Form Example

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8">
    <title>Basic Form</title>
  </head>
  <body>
    <h2>Login</h2>
    <form>
      <label for="username">Username:</label><br>
      <input type="text" id="username" name="username"><br><br>

      <label for="password">Password:</label><br>
      <input type="password" id="password" name="password"><br><br>

      <input type="submit" value="Submit">
    </form>
  </body>
</html>
```

**What each part does:**
- `<form>` — wraps all form controls
- `<label>` — text label for an input field; clicking it focuses the input
- `<input type="text">` — single-line text field
- `<input type="password">` — text field that hides characters
- `<input type="submit">` — button that submits the form

---

## `<form>` Attributes

These attributes control **how and where** form data is sent.

| Attribute | Values | Description |
|---|---|---|
| `action` | URL | Where to send the form data on submit |
| `method` | `get` / `post` | HTTP method used to send data |
| `target` | `_blank`, `_self`, `_parent`, `_top` | Where to show the server response |
| `enctype` | see below | How form data is encoded (for `POST` only) |
| `autocomplete` | `on` / `off` | Whether browser auto-fills fields |
| `novalidate` | boolean | Disables browser validation before submit |

### `method` — GET vs POST

| | `GET` | `POST` |
|---|---|---|
| Data location | Appended to URL `?name=value` | Sent in request body (hidden) |
| Visible in URL? | ✅ Yes | ❌ No |
| Use for | Search forms, filters | Login, signup, sensitive data |
| Data limit | Limited (URL length) | No practical limit |
| Secure? | ❌ No — visible in browser history | ✅ More secure |

### `enctype` Values (used with `method="post"`)

| Value | Use When |
|---|---|
| `application/x-www-form-urlencoded` | Default — for regular text data |
| `multipart/form-data` | When form includes **file uploads** |
| `text/plain` | Plain text — rarely used |

```html
<!-- Form that posts data to a server -->
<form action="/login" method="post" autocomplete="off">
  ...
</form>

<!-- Form with file upload -->
<form action="/upload" method="post" enctype="multipart/form-data">
  ...
</form>
```

---

## Form Elements (Complete Reference)

| Element | Description |
|---|---|
| `<label>` | Text label for a form control — links to input via `for` attribute |
| `<input>` | Versatile input field — behaviour changes with `type` attribute |
| `<button>` | Clickable button — more flexible than `<input type="submit">` |
| `<select>` | Dropdown list |
| `<textarea>` | Multi-line text input |
| `<fieldset>` | Groups related form elements with a visible box |
| `<legend>` | Caption/title for a `<fieldset>` |
| `<datalist>` | Pre-defined suggestions for an `<input>` |
| `<output>` | Displays result of a calculation |
| `<option>` | Individual item in a `<select>` dropdown |
| `<optgroup>` | Groups related `<option>` items in a dropdown |

---

## Input Types — Complete Reference

The `<input>` tag's behaviour is controlled entirely by its `type` attribute.

| Input Type | Description | Example |
|---|---|---|
| `text` | Single-line text field | Name, username |
| `password` | Text field that hides characters | Password |
| `email` | Text field that validates email format | user@example.com |
| `number` | Numeric input with optional `min`, `max`, `step` | Age, quantity |
| `date` | Date picker (calendar UI) | Date of birth |
| `time` | Time picker | Appointment time |
| `radio` | One choice from a group (same `name`) | Gender selection |
| `checkbox` | Multiple choices (each independent) | Interests, terms |
| `file` | File upload selector | Profile picture, resume |
| `submit` | Button that submits the form | Submit button |
| `reset` | Button that clears all fields | Reset button |

### Input Type Examples

```html
<!-- Text -->
<input type="text" name="username" placeholder="Enter username">

<!-- Email — browser validates format -->
<input type="email" name="email" placeholder="you@example.com">

<!-- Password — characters are hidden -->
<input type="password" name="password">

<!-- Number with limits -->
<input type="number" name="age" min="1" max="120" step="1">

<!-- Date picker -->
<input type="date" name="dob">

<!-- Radio buttons — only one selectable (same name groups them) -->
<input type="radio" name="gender" value="male" id="male">
<label for="male">Male</label>
<input type="radio" name="gender" value="female" id="female">
<label for="female">Female</label>

<!-- Checkboxes — multiple selectable -->
<input type="checkbox" name="skill" value="html" id="html">
<label for="html">HTML</label>
<input type="checkbox" name="skill" value="css" id="css">
<label for="css">CSS</label>

<!-- File upload -->
<input type="file" name="resume">

<!-- Submit and Reset buttons -->
<input type="submit" value="Send Form">
<input type="reset" value="Clear All">
```

---

## Key Form Elements in Detail

### `<label>`

Links descriptive text to a form control. Clicking the label focuses the input.

```html
<!-- Method 1: using 'for' attribute matching input's 'id' -->
<label for="email">Email Address:</label>
<input type="email" id="email" name="email">

<!-- Method 2: wrapping input inside label -->
<label>
  Email Address:
  <input type="email" name="email">
</label>
```

> Always use `<label>` — it's required for accessibility (screen readers read the label aloud).

---

### `<textarea>`

Multi-line text input — used for addresses, comments, messages, descriptions.

```html
<label for="message">Your Message:</label>
<textarea id="message" name="message" rows="5" cols="40" placeholder="Type here..."></textarea>
```

- `rows` — visible height (number of text lines)
- `cols` — visible width (number of characters)
- Can be resized by the user by default

---

### `<select>` + `<option>` + `<optgroup>`

Creates a dropdown list.

```html
<label for="country">Country:</label>
<select id="country" name="country">
  <optgroup label="Asia">
    <option value="in">India</option>
    <option value="jp">Japan</option>
  </optgroup>
  <optgroup label="Europe">
    <option value="uk">United Kingdom</option>
    <option value="de">Germany</option>
  </optgroup>
</select>
```

- `<optgroup label="...">` — groups options under a heading in the dropdown
- `value` on `<option>` — what gets submitted (can differ from visible text)

---

### `<fieldset>` + `<legend>`

Groups related form fields with a visible border and a title.

```html
<fieldset>
  <legend>Personal Information</legend>
  <label for="name">Name:</label>
  <input type="text" id="name" name="name">
  <label for="dob">Date of Birth:</label>
  <input type="date" id="dob" name="dob">
</fieldset>
```

---

### `<datalist>`

Provides autocomplete suggestions for a text input — user can still type anything.

```html
<label for="browser">Favourite Browser:</label>
<input list="browsers" id="browser" name="browser">
<datalist id="browsers">
  <option value="Chrome">
  <option value="Firefox">
  <option value="Safari">
  <option value="Edge">
</datalist>
```

> The `list` attribute on `<input>` must match the `id` of `<datalist>`.

---

## Complete Advanced Form Example

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8">
    <title>Registration Form</title>
  </head>
  <body>
    <form action="/register" method="post">
      <fieldset>
        <legend>User Personal Information</legend>

        <label for="name">Full Name:</label>
        <input type="text" id="name" name="name" required>

        <label for="email">Email:</label>
        <input type="email" id="email" name="email" required>

        <label for="password">Password:</label>
        <input type="password" id="password" name="pass" required>

        <label for="confirmPassword">Confirm Password:</label>
        <input type="password" id="confirmPassword" name="confirmPass" required>

        <label>Gender:</label>
        <input type="radio" name="gender" value="male" id="male" required>
        <label for="male">Male</label>
        <input type="radio" name="gender" value="female" id="female">
        <label for="female">Female</label>
        <input type="radio" name="gender" value="others" id="others">
        <label for="others">Others</label>

        <label for="dob">Date of Birth:</label>
        <input type="date" id="dob" name="dob" required>

        <label for="address">Address:</label>
        <textarea id="address" name="address" rows="3" required></textarea>

        <input type="submit" value="Register">
        <input type="reset" value="Clear">
      </fieldset>
    </form>
  </body>
</html>
```

---

## Common Input Attributes

| Attribute | Description | Example |
|---|---|---|
| `name` | Key used when form data is submitted — required for data to be sent | `name="email"` |
| `id` | Links input to its `<label>` via `for` attribute | `id="email"` |
| `value` | Default/pre-filled value | `value="India"` |
| `placeholder` | Hint text shown inside empty field | `placeholder="Enter name"` |
| `required` | Field must be filled before submit | `required` |
| `disabled` | Field is shown but cannot be edited | `disabled` |
| `readonly` | Field can be seen and submitted but not edited | `readonly` |
| `min` / `max` | Minimum/maximum value for number or date inputs | `min="0" max="100"` |
| `maxlength` | Maximum number of characters allowed | `maxlength="50"` |
| `autofocus` | Field is automatically focused when page loads | `autofocus` |

---

## Best Practices

✅ Always use `<label>` with every input — critical for accessibility  
✅ Always add `name` attribute to inputs — without it, data won't be submitted  
✅ Use `required` on mandatory fields to prevent empty submissions  
✅ Use `type="email"`, `type="number"`, `type="date"` — browser validates automatically  
✅ Use `method="post"` for sensitive data (passwords, personal info)  
✅ Use `<fieldset>` + `<legend>` to group related fields in long forms  
✅ Use `placeholder` for hints, but never as a replacement for `<label>`  

❌ Don't use `method="get"` for passwords or sensitive data — it shows in the URL  
❌ Don't forget `enctype="multipart/form-data"` when handling file uploads  
❌ Don't rely only on browser validation — always validate on the server too  
❌ Don't use `placeholder` instead of `<label>` — placeholder disappears on typing  

---

## Common Beginner Mistakes

- **Missing `name` attribute** — the input exists visually but its data is never submitted
- **Confusing `id` and `name`** — `id` links to `<label>`; `name` is the key sent with form data — both are needed
- **Radio buttons with different `name` values** — they won't be grouped; multiple can be selected
- **Using `<button>` inside a `<form>` without `type="button"`** — it defaults to `type="submit"` and submits the form unexpectedly
- **Forgetting `enctype` for file uploads** — files won't be sent to the server without it
- **Using `placeholder` as a label** — text disappears when typing, breaking accessibility

---

## Interview / Important Notes

- `<form>` `method` attribute: `get` (data in URL) vs `post` (data in request body)
- `action` = URL where form data is sent; if omitted, sends to the same page
- `required` — boolean attribute; no value needed
- Radio buttons are grouped by sharing the same `name` attribute
- `<label for="id">` links to `<input id="id">` — clicking label focuses the input
- `enctype="multipart/form-data"` is **mandatory** for file upload forms
- `<fieldset>` groups fields; `<legend>` is its title
- `<datalist>` gives suggestions but doesn't restrict what the user types
- `<select>` restricts the user to predefined options only

---

## Mini Practice

Build a **Contact Us** form with the following fields:

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8">
    <title>Contact Us</title>
  </head>
  <body>
    <h2>Contact Us</h2>
    <form action="/contact" method="post">
      <fieldset>
        <legend>Your Details</legend>

        <label for="fname">Full Name:</label><br>
        <input type="text" id="fname" name="fullname" placeholder="John Doe" required><br><br>

        <label for="email">Email:</label><br>
        <input type="email" id="email" name="email" placeholder="you@example.com" required><br><br>

        <label for="subject">Subject:</label><br>
        <select id="subject" name="subject">
          <option value="general">General Enquiry</option>
          <option value="support">Technical Support</option>
          <option value="billing">Billing</option>
        </select><br><br>

        <label for="message">Message:</label><br>
        <textarea id="message" name="message" rows="5" placeholder="Write your message..." required></textarea><br><br>

        <input type="submit" value="Send Message">
        <input type="reset" value="Clear Form">
      </fieldset>
    </form>
  </body>
</html>
```

**Challenge:** Add a checkbox asking "I agree to the Terms and Conditions" with `required`, and a file input asking the user to optionally attach a document. Remember to add `enctype="multipart/form-data"` to the form when you do.