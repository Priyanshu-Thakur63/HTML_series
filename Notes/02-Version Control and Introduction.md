# Git — Repositories & Commands

---

## What is a Git Repository?

- Storage space for a project's files and their **complete history of changes**
- Enables version control — go back to any previous state
- Supports collaboration — multiple developers without overwriting each other
- Can be **cloned** to create copies on different machines

---

## Types of Git Repositories

### By location
| Type | Description |
|---|---|
| **Local** | Stored on your own computer; no internet needed. The `.git` folder inside your project is the local repo |
| **Remote** | Hosted on a server (GitHub, GitLab, Bitbucket); enables team collaboration via push, pull, fetch |

### By structure
| | Bare Repository | Non-Bare Repository |
|---|---|---|
| Contains | Version history + Git data only | Working files + Git history |
| Used for | Servers / central collaboration | Local development and testing |
| Edit files? | No — only push and fetch | Yes — supports all Git operations |
| Extension | Usually ends in `.git` | No `.git` extension |

---

## Git Commands

### Initialise a repository
```bash
git init
```
Sets up a new Git repo in the current project folder.

---

### Stage files — `git add`
```bash
git add file_name          # add a specific file
git add .                  # add all changes in current directory
git add --all              # add all new, modified, and deleted files
git add *.txt              # add all .txt files in current directory
git add docs/*.txt         # add all .txt files inside docs/ folder
git add docs/              # add all files inside docs/ folder
git add "*.txt"            # add all .txt files across the whole project
```

---

### Commit staged changes — `git commit`
```bash
git commit -m "your message here"
```
Saves staged changes to the repository with a descriptive message.

> Flow: Working area → `git add` → Staging area → `git commit` → Commit history

---

### Push to remote — `git push`
```bash
git push -u origin master
```
Pushes all commits from your local `master` branch to the remote repository.

---

### Pull from remote — `git pull`
```bash
git pull
```
Fetches and merges changes from the remote repo into your local copy. Keeps your repo in sync.

---

### Check status — `git status`
```bash
git status
```
Shows which files are staged, unstaged, or untracked.

---

### View commit history — `git log`
```bash
git log
```
Displays all past commits with author info, timestamps, and commit messages.

---

### Merge branches — `git merge`
```bash
git merge <branch-name>
```
Combines changes from the specified branch into your current branch. History is preserved.

---

### Switch branch or commit — `git checkout`
```bash
git checkout <hash-code>
```
Moves the HEAD pointer to a different branch or past commit. Does **not** permanently roll back — use it to explore or temporarily switch states.  
Get the hash code from `git log`.

---

### Ignore files — `.gitignore`
Create a file named `.gitignore` in your project root and list any files or folders you don't want tracked or uploaded:
```
node_modules/
.env
*.log
dist/
```

---

## Quick Reference — All Commands

| Command | Purpose |
|---|---|
| `git init` | Initialise a new local repository |
| `git add .` | Stage all changes |
| `git add <file>` | Stage a specific file |
| `git add --all` | Stage all new, modified, deleted files |
| `git commit -m "msg"` | Commit staged changes with a message |
| `git push -u origin master` | Push local commits to remote |
| `git pull` | Fetch and merge remote changes |
| `git status` | Check staged / unstaged / untracked files |
| `git log` | View full commit history |
| `git merge <branch>` | Merge a branch into current branch |
| `git checkout <hash>` | Switch to a past commit or branch |
| `.gitignore` | List files to exclude from tracking |



# HTML5 & First Web Page — Notes

---

## What is HTML5?

- Fifth version of **HyperText Markup Language**
- Defines how content on a webpage is structured and displayed
- Key improvements over older HTML:
  - Multimedia support — embed audio/video without plugins
  - New form controls — date, email input types
  - Web storage — store data offline for better performance
  - Semantic elements — `<header>`, `<footer>` for clearer structure
  - Better mobile performance

---

## Basic HTML5 Page Structure

```html
<!DOCTYPE html>
<html>
  <head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Simple HTML Page</title>
  </head>
  <body>
    <header>
      <h1>Hello, World!</h1>
    </header>
    <main>
      <p>This is a simple HTML5 page.</p>
    </main>
    <footer>
      <p>Footer content here</p>
    </footer>
  </body>
</html>
```

- `<!DOCTYPE html>` — declares it's an HTML5 document
- `<html>` — wraps all content
- `<head>` — metadata (charset, viewport, title)
- `<body>` — visible page content
- `charset="UTF-8"` — prevents encoding issues
- `viewport` meta tag — makes page mobile-responsive

---

## New Elements in HTML5

### Structural / Semantic
| Tag | Purpose |
|---|---|
| `<header>` | Introductory content, headings, nav links |
| `<footer>` | Closing content — author info, copyright |
| `<main>` | Central, most important content of the page |
| `<nav>` | Groups navigation links |
| `<section>` | Organises related content into thematic blocks |
| `<article>` | Independent, self-contained content (posts, articles) |
| `<aside>` | Secondary or related supporting content |
| `<figure>` | Groups self-contained media (images, diagrams, code) |
| `<figcaption>` | Caption or description for a `<figure>` |

### Text & Inline
| Tag | Purpose |
|---|---|
| `<mark>` | Highlights or emphasises specific text |
| `<time>` | Represents dates or times (human + machine readable) |
| `<bdi>` | Isolates text with unknown/mixed text direction |
| `<wbr>` | Adds optional line-break position in long words |

### Interactive / Form
| Tag | Purpose |
|---|---|
| `<details>` | Expandable/collapsible content section |
| `<summary>` | Clickable heading for a `<details>` element |
| `<datalist>` | Autocomplete suggestions for an `<input>` |
| `<output>` | Displays results of calculations or scripts |
| `<progress>` | Visual progress bar for a task |

### Media
| Tag | Purpose |
|---|---|
| `<audio>` | Embeds audio content |
| `<video>` | Embeds video content |
| `<source>` | Defines media sources for `<audio>` and `<video>` |
| `<track>` | Provides captions/subtitles for video |
| `<embed>` | Inserts external resources (media players, apps) |
| `<canvas>` | Draw dynamic graphics using JavaScript |
| `<svg>` | Embeds scalable vector graphics |

---

## Deprecated Elements (removed in HTML5)

| Old Tag | Replacement |
|---|---|
| `<acronym>` | `<abbr>` |
| `<applet>` | `<object>` |
| `<basefont>` | CSS |
| `<big>` | CSS `font-size` |
| `<center>` | CSS `text-align` |
| `<dir>` | `<ul>` |
| `<font>` | CSS |
| `<frame>`, `<frameset>`, `<noframes>` | No replacement |
| `<strike>` | CSS, `<s>`, or `<del>` |
| `<tt>` | CSS or `<code>` |

---

## HTML5 — Advantages & Disadvantages

| Advantages | Disadvantages |
|---|---|
| Cross-platform — works on all major browsers and devices | Older browsers may not support all features |
| Geolocation — can access user's location | Older mobile devices may struggle with HTML5 |
| Offline support via Web Storage or AppCache | Web Storage can pose security risks if misused |
| Semantic tags = cleaner, more readable code | Advanced APIs can be complex for beginners |
| Optimised for mobile performance | IE 8 and below have poor HTML5 support |

---

## Code Examples

### Embedding a video
```html
<video width="320" height="100" controls>
  <source src="movie.mp4" type="video/mp4">
  Your browser does not support the video tag.
</video>
```
- `controls` adds play, pause, volume buttons
- `<source>` specifies the file and format
- Fallback text shown if video is unsupported

### Drawing with `<canvas>`
```html
<canvas id="myCanvas" width="100" height="100"></canvas>
<script>
  var canvas = document.getElementById("myCanvas");
  var ctx = canvas.getContext("2d");
  ctx.fillStyle = "blue";
  ctx.fillRect(50, 50, 100, 100);
</script>
```
- `getContext("2d")` sets up a 2D drawing context
- `fillRect` draws a filled rectangle

### Progress bar
```html
<progress value="70" max="100"></progress>
```
- `value` = current progress
- `max` = total value

---

## Best Practices

- Use **semantic tags** (`<header>`, `<footer>`, `<article>`, `<section>`) for better SEO and accessibility
- Always include `<meta charset="UTF-8">` to avoid encoding issues
- Add **viewport meta tag** for mobile responsiveness
- Test across multiple browsers for cross-browser compatibility

---

## First Web Page — "Hello World"

### Minimal structure
```html
<!DOCTYPE html>
<html>
  <head>
    <title>First Web Page</title>
  </head>
  <body>
    Hello World!
  </body>
</html>
```

### HTML heading tags — `<h1>` to `<h6>`
```html
<h1>Hello World!</h1>   <!-- largest -->
<h2>Hello World!</h2>
<h3>Hello World!</h3>
<h4>Hello World!</h4>
<h5>Hello World!</h5>
<h6>Hello World!</h6>   <!-- smallest -->
```
- `<h1>` = largest and most emphasised
- `<h6>` = smallest and least emphasised
- Use headings to organise content hierarchy, not just for size

### Steps to create your first webpage
1. Open a text editor — Notepad, TextEdit, VS Code, Sublime Text
2. Create a file named `index.html`
3. Write your HTML structure with `<!DOCTYPE html>`, `<html>`, `<head>`, `<body>`
4. Save and open the file in a browser to preview