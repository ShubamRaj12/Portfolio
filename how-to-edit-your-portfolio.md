# How to Edit MY Portfolio

my portfolio is one file, `index.html`. It's plain text underneath — no special software required to edit it, and no build step. Change the text, save, refresh my browser, done.

## What I need

- **A text editor.** [VS Code](https://code.visualstudio.com) (free) is the easiest — it color-codes the HTML so it's much harder to break something by accident. Notepad (Windows) or TextEdit (Mac, in plain-text mode) also work in a pinch.
- **A web browser** to preview — just double-click `index.html` to open it.

Do **not** use Microsoft Word or a rich-text editor — they'll corrupt the file.

## The core workflow

1. Open `index.html` in your text editor.
2. Press **Ctrl+F** (Windows) or **Cmd+F** (Mac) and search for words you actually see on the live page — e.g. search "Boston-based analyst" to jump straight to your About section.
3. Edit the text between the tags (the `<...>` bits). Leave the tags themselves alone.
4. Save the file.
5. Flip to your browser tab and refresh (F5 / Cmd+R). If you opened the file fresh, just reopen it.

That's the entire loop. Everything below is just "where to search for" and "what template to copy."

---

## Editing existing text

Almost everything visible is plain text sitting between a `>` and a `<`. For example, your hero tagline looks like this in the file:

```html
<p class="hero-dek">Two years catching fraud and compliance gaps in insurance claims queues, now backed by an M.S. in Analytics from Northeastern University. I build the kind of dashboards and models that turn raw transaction data into a decision.</p>
```

To change it, search for a phrase like "catching fraud" and just retype the sentence between `<p class="hero-dek">` and `</p>`. Same pattern everywhere — About, Experience bullets, Education — find a phrase you recognize, edit the words, keep the tags on either side untouched.

---

## Adding a new project card

This is the one you'll use soon. Search for `Air Quality Statistical Analysis` — you'll land on its card:

```html
<div class="pcard">
  <h3>Air Quality Statistical Analysis</h3>
  <div class="tools">R · Regression · ANOVA · Hypothesis Testing</div>
  <p class="desc">Applied regression, ANOVA, and chi-square testing to pollutant data (CO, Benzene, NOx) to uncover traffic-driven and seasonal air-quality patterns.</p>
</div>
```

**To add a brand new card**, copy that whole block (from `<div class="pcard">` to its matching `</div>`), paste it right after, and edit the three inner pieces: the title, the tools line, and the description. Leave the `<div class="pcard">` and `</div>` wrapper exactly as-is.

**If a project later gets its own live page** (like I built for HIV and Food Insecurity), copy this version instead, which has the green badge and a working link:

```html
<div class="pcard is-live">
  <span class="badge"><span class="d"></span>LIVE · REAL DATABASE</span>
  <h3>Food Insecurity Alert &amp; Assistance Network</h3>
  <div class="tools">SQL · SQLite · ER Design</div>
  <p class="desc">A 7-table relational database linking individuals, food banks, and partner NGOs through a shared location model.</p>
  <a class="pcard-link" href="food_dashboard.html" target="_blank">Open live SQL console →</a>
</div>
```

Change `href="food_dashboard.html"` to whatever the new file is named (it must sit in the same folder), and change the link text and badge label to match.

---

## Editing MY skills list

Search for `skill-label`. Each group looks like this:

```html
<div class="skill-group">
  <div class="skill-label">Languages &amp; Querying</div>
  <div class="pill-row"><span class="pill">SQL</span><span class="pill">Python</span><span class="pill">R</span></div>
</div>
```

Add a new skill by copying a `<span class="pill">...</span>` and changing the word inside. Add a whole new row by copying the entire `skill-group` block.

---

## Editing contact info

Search for `mailto:`. Each contact method is one small block:

```html
<a class="contact-card" href="mailto:shubamraj99088@gmail.com">
  <div class="clabel">Email</div>
  <div class="cvalue">shubamraj99088@gmail.com</div>
</a>
```

Change the email in **two** places — inside `href="mailto:..."` and in the visible `cvalue` line. Same idea for the phone (search `tel:`) and LinkedIn (search `linkedin.com`) cards.

---

## Adjusting colors

Near the very top of the file, search for `:root{`. That's your entire color palette in one place:

```css
--primary:#1F2937;   /* card backgrounds */
--secondary:#4B5563; /* borders, muted text */
--bg:#111827;        /* page background */
--accent:#F59E0B;    /* links, buttons, highlights (your gold) */
--text:#F3F4F6;      /* main text color */
--text-dim:#9CA3AF;  /* softer/secondary text */
```

Change any hex code here and it updates everywhere that color is used on the page — you don't need to hunt down every individual spot.

---

## Staying safe

- **Every `<div>` needs a matching `</div>`** somewhere later. If you delete one but not the other, the layout below it can visually break. When in doubt, delete in matched pairs — select from the opening tag to its closing tag together.
- **Keep quotation marks in pairs.** `href="food_dashboard.html"` needs both quote marks.
- **Save a backup copy before a big edit.** Duplicate `index.html` and rename the copy `index_backup.html` first, so you can always revert.
- If the page looks visibly broken after an edit (text in the wrong place, missing sections), that almost always means a tag got deleted or left unclosed — undo (Ctrl+Z) in your editor and try again more surgically.

