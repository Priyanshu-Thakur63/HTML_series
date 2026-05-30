# HTML DOCTYPE (Document Type Declaration)

**Tags:** #html #web-development #basics #gfg  
**Related:** [[HTML Structure]] | [[HTML Tags]] | [[Browser Rendering]]

---

## What is DOCTYPE?

`<!DOCTYPE html>` is a special instruction placed at the **very top** of every HTML file — before even the `<html>` tag.

It tells the web browser:
- What version of HTML the page is written in
- How it should **interpret and render** the content

> **Important:** `<!DOCTYPE>` is NOT an HTML tag. It is a **declaration / instruction** to the browser.

---

## Why is it Used?

Without `<!DOCTYPE>`, browsers don't know which rules to follow when displaying your page. This causes:

- Broken layouts
- CSS not working correctly
- JavaScript features failing
- Pages looking different across Chrome, Firefox, Safari, etc.

**Real-world analogy:** Think of `<!DOCTYPE>` like telling a chef *which recipe book to use* before they start cooking. Without it, they might guess — and the dish could turn out completely different.

---

## Syntax / Structure

```html
<!DOCTYPE html>
```

That's it for HTML5 — just one short line at the top of your file.

### Line-by-line Breakdown

| Part | Meaning |
|---|---|
| `<!` | Signals this is a declaration, not a regular tag |
| `DOCTYPE` | Keyword telling the browser this is a document type declaration |
| `html` | Specifies the document type is HTML (HTML5 in modern usage) |

> **Note:** `<!DOCTYPE>` is **NOT case-sensitive**.  
> `<!DOCTYPE html>`, `<!doctype html>`, and `<!Doctype HTML>` all work.

---

## Full HTML5 Example

```html
<!DOCTYPE html>
<html>
  <body>
    <p>Welcome to my website</p>
  </body>
</html>
```

**What happens here:**
- `<!DOCTYPE html>` → triggers **Standards Mode** in the browser
- Browser uses modern HTML5 rules to render the page
- CSS, Flexbox, Grid, JavaScript all work correctly

---

## Key Concepts

### Browser Rendering Modes

When the browser reads your HTML, it chooses one of two modes based on whether `<!DOCTYPE>` is present:

| Mode | Triggered By | Behavior |
|---|---|---|
| **Standards Mode** | `<!DOCTYPE html>` is present | Follows modern web standards (HTML5) |
| **Quirks Mode** | `<!DOCTYPE>` is missing | Mimics old/broken browser behavior for legacy sites |

> Always aim for **Standards Mode** — it's predictable, modern, and consistent.

---

## What Happens Without DOCTYPE?

If you forget `<!DOCTYPE html>`, the browser enters **Quirks Mode**, which causes:

- **Layout problems** — CSS properties like `box-sizing`, `margins`, and `width` may behave unexpectedly
- **Cross-browser inconsistency** — Chrome, Firefox, and Safari may all render the page differently
- **Modern features break** — Flexbox, CSS Grid, and some JavaScript APIs may not work correctly
- **Hard to debug** — bugs appear randomly and are difficult to trace

<details>
<summary>Example: What goes wrong in Quirks Mode</summary>

In Quirks Mode:
- A `div` with `width: 100px` and `padding: 10px` might calculate its total width differently than expected
- Fonts might render at different sizes
- Line heights may be inconsistent
- Tables may behave like they did in the late 1990s

All of this is avoided simply by writing `<!DOCTYPE html>` at the top.

</details>

---

## DOCTYPE for Different HTML / XHTML Versions

Modern projects always use HTML5. But here's the full reference table in case you work on legacy codebases:

| HTML Version | DOCTYPE Declaration |
|---|---|
| **HTML5** ✅ | `<!DOCTYPE html>` |
| HTML 4.01 Strict | `<!DOCTYPE HTML PUBLIC "-//W3C//DTD HTML 4.01//EN" "http://www.w3.org/TR/html4/strict.dtd">` |
| HTML 4.01 Transitional | `<!DOCTYPE HTML PUBLIC "-//W3C//DTD HTML 4.01 Transitional//EN" "http://www.w3.org/TR/html4/loose.dtd">` |
| HTML 4.01 Frameset | `<!DOCTYPE HTML PUBLIC "-//W3C//DTD HTML 4.01 Frameset//EN" "http://www.w3.org/TR/html4/frameset.dtd">` |
| XHTML 1.0 Strict | `<!DOCTYPE html PUBLIC "-//W3C//DTD XHTML 1.0 Strict//EN" "http://www.w3.org/TR/xhtml1/DTD/xhtml1-strict.dtd">` |
| XHTML 1.0 Transitional | `<!DOCTYPE html PUBLIC "-//W3C//DTD XHTML 1.0 Transitional//EN" "http://www.w3.org/TR/xhtml1/DTD/xhtml1-transitional.dtd">` |
| XHTML 1.0 Frameset | `<!DOCTYPE html PUBLIC "-//W3C//DTD XHTML 1.0 Frameset//EN" "http://www.w3.org/TR/xhtml1/DTD/xhtml1-frameset.dtd">` |
| XHTML 1.1 | `<!DOCTYPE html PUBLIC "-//W3C//DTD XHTML 1.1//EN" "http://www.w3.org/TR/xhtml11/DTD/xhtml11.dtd">` |

> For any **new website**, always use `<!DOCTYPE html>` (HTML5). The older declarations are long, complex, and unnecessary for modern development.

---

## Best Practices

✅ **Always include `<!DOCTYPE html>`** at the very top of every HTML file  
✅ **Use HTML5 DOCTYPE** for all new projects — it's the current standard  
✅ **Place it on line 1** — before `<html>`, `<head>`, or any other tag  
✅ **Validate your HTML** using the W3C Validator: [validator.w3.org](https://validator.w3.org)

❌ **Don't place DOCTYPE after the `<html>` tag** — it won't work correctly  
❌ **Don't skip it** even if the page "seems to work" — Quirks Mode causes subtle bugs  
❌ **Don't use old HTML 4 or XHTML DOCTYPEs** for new projects — unnecessarily complex  

---

## Common Beginner Mistakes

- **Forgetting DOCTYPE entirely** — page may look fine in one browser but break in another
- **Placing DOCTYPE after the `<html>` tag** — declaration must be the very first line
- **Confusing DOCTYPE with an HTML tag** — it is a declaration, not a tag; it has no closing counterpart
- **Using old HTML 4 DOCTYPE** on a new project — unnecessary; `<!DOCTYPE html>` covers HTML5

---

## Interview / Important Notes

- `<!DOCTYPE html>` is the correct declaration for **HTML5**
- It is **not** an HTML tag — it is a **declaration**
- It is **not case-sensitive** — `<!doctype html>` is valid
- It triggers **Standards Mode** in browsers
- Without it, browsers may fall into **Quirks Mode**, causing inconsistent rendering
- HTML5's DOCTYPE is intentionally short — older HTML versions had long, complex DTD URLs
- DOCTYPE does **not** tell the browser "this is HTML5" explicitly — it tells the browser *which rendering mode* to use

---

## Mini Practice

Try this yourself:

1. Create a file called `index.html`
2. Write the full HTML5 boilerplate with `<!DOCTYPE html>`
3. Add a heading and a paragraph inside `<body>`
4. Open it in your browser — it should render cleanly

```html
<!DOCTYPE html>
<html>
  <head>
    <title>My First Page</title>
  </head>
  <body>
    <h1>Hello, World!</h1>
    <p>This page uses HTML5 DOCTYPE.</p>
  </body>
</html>
```

**Challenge:** Try removing `<!DOCTYPE html>` and inspect the page in browser DevTools. Check under **Rendering** settings or use `document.compatMode` in the console — it will say `"BackCompat"` in Quirks Mode and `"CSS1Compat"` in Standards Mode.

---

# HTML Basics

**Tags:** #html #web-development #basics #gfg  
**Related:** [[HTML DOCTYPE]] | [[HTML Attributes]] | [[HTML Forms]] | [[CSS Basics]]

---

## What is HTML?

**HTML (HyperText Markup Language)** is the standard language used to create and structure web pages.

- It uses **elements and tags** to define the layout of a webpage
- Tells the browser what to display — text, images, links, videos, etc.
- Used in over **95% of all web pages** — it is the absolute foundation of the web

> **Think of it like this:** If a website were a house, HTML is the **skeleton/structure** — the walls, floors, and rooms. CSS is the paint and decoration. JavaScript is the electricity and plumbing.

---

## HTML Document Structure

Every HTML page follows the same basic skeleton. Understanding this structure is the first thing you must master.

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>My Page Title</title>
  </head>
  <body>
    <!-- Page content goes here -->
    <p>GeeksforGeeks is an online study platform</p>
  </body>
</html>
```

### Structure Breakdown — Tag by Tag

| Tag | Role | Visible on Page? |
|---|---|---|
| `<!DOCTYPE html>` | Declares HTML5 to the browser | ❌ No |
| `<html>` | Root element — wraps everything | ❌ No |
| `<head>` | Contains page metadata (title, charset, viewport) | ❌ No |
| `<meta charset="UTF-8">` | Sets character encoding — supports all languages/symbols | ❌ No |
| `<meta name="viewport" ...>` | Makes page responsive on mobile devices | ❌ No |
| `<title>` | Text shown in the browser tab | ❌ (tab only) |
| `<body>` | Everything the user actually sees on the page | ✅ Yes |

> **Rule of thumb:** Everything inside `<head>` is for the **browser**. Everything inside `<body>` is for the **user**.

<details>
<summary>What does <code>lang="en"</code> do?</summary>

The `lang` attribute on `<html>` tells the browser (and screen readers) what language the page is written in. `"en"` means English. This helps with:
- Accessibility (screen readers pronounce words correctly)
- SEO (search engines better understand the content)
- Browser translation features

</details>

---

## HTML Headings

Headings define the **hierarchy and importance** of content on a page. There are 6 levels.

### Syntax

```html
<h1>Largest Heading</h1>
<h2>Second Level</h2>
<h3>Third Level</h3>
<h4>Fourth Level</h4>
<h5>Fifth Level</h5>
<h6>Smallest Heading</h6>
```

### Full Example

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8">
    <title>Headings</title>
  </head>
  <body>
    <h1>Heading 1 (h1)</h1>
    <h2>Heading 2 (h2)</h2>
    <h3>Heading 3 (h3)</h3>
    <h4>Heading 4 (h4)</h4>
    <h5>Heading 5 (h5)</h5>
    <h6>Heading 6 (h6)</h6>
  </body>
</html>
```

### Heading Size Reference

| Tag | Use Case | Relative Size |
|---|---|---|
| `<h1>` | Main page title — use only **once** per page | Largest |
| `<h2>` | Major section headings | ↓ |
| `<h3>` | Sub-sections within h2 | ↓ |
| `<h4>` | Sub-sub-sections | ↓ |
| `<h5>` | Rarely used | ↓ |
| `<h6>` | Least important heading | Smallest |

**Best Practices:**
- ✅ Use `<h1>` only **once** per page (important for SEO)
- ✅ Use headings in order — don't skip from `<h1>` to `<h4>`
- ❌ Don't use headings just to make text big — use CSS for styling

---

## HTML Paragraphs — `<p>`

The `<p>` tag wraps a block of text into a paragraph. The browser automatically adds spacing above and below it.

### Syntax

```html
<p>Your paragraph text here.</p>
```

### Example

```html
<body>
  <p>HTML stands for HyperText Markup Language.</p>
  <p>It is used to design web pages using a markup language.</p>
</body>
```

---

## HTML Line Break — `<br>`

The `<br>` tag inserts a **single line break** inside content — like pressing Enter in a text editor.

- It is a **self-closing / void tag** — no closing tag needed
- Use it inside a `<p>` when you want a new line *without* starting a new paragraph

### Syntax

```html
<br>
```

### Example

```html
<p>
  HTML stands for HyperText Markup Language.<br>
  It is used to design web pages.<br>
  HTML is a combination of Hypertext and Markup language.
</p>
```

**Output:** Each sentence appears on its own line within the same paragraph block.

> **When to use `<br>` vs a new `<p>`:**
> - Use `<br>` for line breaks *within* a thought (e.g., a poem, an address)
> - Use a new `<p>` for a completely new idea or paragraph

---

## HTML Horizontal Rule — `<hr>`

The `<hr>` tag draws a **horizontal line** across the page — used to visually separate sections of content.

- Self-closing / void tag — no closing tag needed
- No required attributes

### Syntax

```html
<hr>
```

### Example

```html
<body>
  <p>Section One content here.</p>

  <hr>

  <p>Section Two content here.</p>

  <hr>

  <p>Section Three content here.</p>
</body>
```

**Output:** A full-width horizontal line appears between each section.

---

## HTML Comments

HTML comments are notes written in the code that are **completely invisible to the user** in the browser. Only developers can see them in the source code.

### Syntax

```html
<!-- Single-line comment -->

<!--
  Multi-line comment
  spanning multiple lines
-->
```

### Example

```html
<body>
  <!-- This heading introduces the page -->
  <h1>Welcome to GeeksforGeeks</h1>

  <!-- This paragraph describes the platform -->
  <p>Learn HTML, CSS, and JavaScript here.</p>
</body>
```

### Why Use Comments?

| Use Case | Example |
|---|---|
| Document what a section does | `<!-- Navigation menu starts here -->` |
| Temporarily disable code | `<!-- <p>Old content</p> -->` |
| Leave notes for teammates | `<!-- TODO: Add image here -->` |
| Mark start/end of sections | `<!-- ===== FOOTER ===== -->` |

**Best Practices:**
- ✅ Explain the *why*, not the *what* — the code shows what; comments explain the reasoning
- ✅ Keep comments brief and accurate
- ✅ Update comments when you change the code
- ❌ Don't over-comment obvious things: `<!-- This is a paragraph -->` on a `<p>` tag is pointless
- ❌ Don't put sensitive information (passwords, API keys) in comments — they're visible in page source

---

## HTML Images — `<img>`

The `<img>` tag is used to **embed an image** into a webpage.

- It is a **self-closing / void tag** — no closing tag needed
- The image source is provided via the `src` attribute

### Syntax

```html
<img src="path-to-image.png" alt="Description of image">
```

### Attribute Breakdown

| Attribute | Required? | Purpose |
|---|---|---|
| `src` | ✅ Yes | Path or URL of the image |
| `alt` | ✅ Best practice | Text shown if image fails to load; used by screen readers |
| `width` | Optional | Set display width in pixels |
| `height` | Optional | Set display height in pixels |

### Example

```html
<!-- Image from a local file -->
<img src="logo.png" alt="Company Logo">

<!-- Image from the internet -->
<img src="https://example.com/photo.jpg" alt="A beautiful photo">

<!-- Image with size specified -->
<img src="banner.jpg" alt="Banner" width="800" height="300">
```

**Best Practices:**
- ✅ Always include `alt` — required for accessibility and SEO
- ✅ Use descriptive alt text: `alt="Red sports car"` not `alt="car"`
- ❌ Don't leave `alt` empty unless the image is purely decorative

---

## Viewing HTML Source Code

Two essential browser tools every developer uses constantly:

### 1. View Full Page Source

**Shortcut:** `Ctrl + U` (Windows/Linux) | `Cmd + Option + U` (Mac)  
**Or:** Right-click anywhere on page → **View Page Source**

- Opens a new tab showing the complete raw HTML of the page
- Useful for seeing how real websites are built

### 2. Inspect Element (DevTools)

**Shortcut:** `F12` or `Ctrl + Shift + I`  
**Or:** Right-click on any element → **Inspect**

- Opens browser DevTools
- Shows the HTML *and* CSS for any specific element
- You can **edit the HTML/CSS live** to test changes (changes don't save — they're temporary)
- Essential tool for debugging layouts and styles

> **Pro tip:** Inspecting real websites is one of the best ways to learn HTML and CSS. Pick any site you admire and study how it's built.

---

## Void / Self-Closing Tags (Quick Reference)

Some HTML tags don't wrap content — they stand alone. These are called **void elements** or **self-closing tags**.

| Tag | Purpose |
|---|---|
| `<br>` | Line break |
| `<hr>` | Horizontal rule / divider |
| `<img>` | Image |
| `<meta>` | Metadata |
| `<link>` | External resource (CSS file) |
| `<input>` | Form input field |

> These tags have **no closing tag**. Writing `</br>` or `</img>` is incorrect HTML.

---

## Best Practices — Summary

✅ Always start with `<!DOCTYPE html>`  
✅ Always include `<html>`, `<head>`, and `<body>` tags  
✅ Always add `<meta charset="UTF-8">` to support special characters  
✅ Always add `<meta name="viewport">` for mobile responsiveness  
✅ Always add `alt` attribute to every `<img>` tag  
✅ Use headings in logical order (`h1` → `h2` → `h3`)  
✅ Use comments to document complex sections of code  

❌ Don't use heading tags just to make text bigger — use CSS  
❌ Don't use `<br>` repeatedly to create spacing — use CSS margins  
❌ Don't skip `alt` on images  
❌ Don't put multiple `<h1>` tags on one page  

---

## Common Beginner Mistakes

- **Forgetting to close tags** — `<p>Hello` without `</p>` can break layouts
- **Nesting tags incorrectly** — `<b><i>text</b></i>` is wrong; should be `<b><i>text</i></b>`
- **Confusing `<br>` with `<hr>`** — `<br>` = line break (invisible), `<hr>` = visible horizontal line
- **Using `<h1>` multiple times** — use only once per page for SEO and accessibility
- **Missing `alt` on images** — breaks accessibility and hurts SEO
- **Putting content outside `<body>`** — all visible content must go inside `<body>`

---

## Interview / Important Notes

- HTML stands for **HyperText Markup Language**
- `<head>` content is NOT displayed on the page — it holds metadata
- `<body>` contains everything the user sees
- `<br>`, `<hr>`, `<img>`, `<meta>` are **void elements** — no closing tag
- HTML has **6 heading levels**: `<h1>` (largest) to `<h6>` (smallest)
- Comments syntax: `<!-- comment here -->` — not visible in the browser
- `src` = source of an image; `alt` = fallback text and accessibility description
- `Ctrl + U` = view page source | `F12` = open DevTools

---

## Mini Practice

Build this simple webpage from scratch without looking at the examples:

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>About Me</title>
  </head>
  <body>

    <!-- Main heading -->
    <h1>About Me</h1>

    <hr>

    <!-- Section: Bio -->
    <h2>Who Am I?</h2>
    <p>
      My name is [Your Name].<br>
      I am learning web development.<br>
      I am currently studying HTML basics.
    </p>

    <hr>

    <!-- Section: Goals -->
    <h2>My Goals</h2>
    <p>I want to build real-world websites and become a developer.</p>

    <!-- Profile image -->
    <img src="https://via.placeholder.com/150" alt="Profile Photo">

  </body>
</html>
```

**Challenge:** Add a third section with an `<h2>` heading, a paragraph, and a `<hr>` divider. Practice adding comments throughout to label each section.

---
