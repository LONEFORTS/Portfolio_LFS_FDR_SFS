# Ayush Lone — Portfolio

A single-file, dependency-free portfolio. Everything lives in `index.html`
(one `<style>` block in the head, one `<script>` block at the end of the body,
JavaScript wrapped in an IIFE). No frameworks, no build step.

## Where to edit things

### Colour tokens
Open `index.html` and look at the top of the `<style>` block, in `:root`:

    --bg        page background (currently #000000)
    --ink       primary text (currently #ffffff)
    --ink-2     readable secondary text
    --ink-3     faint / decorative text
    --line      hairline borders
    --silver    archival certificate ornament (muted silver)
    --champagne archival certificate ornament (muted champagne-gold)

### Navigation
Desktop links: search for `<ul class="nav-links">`.
Mobile overlay links: search for `id="mobileMenu"`.
Footer links: search for `class="footer-nav"`.
Edit all three together so they stay in sync.

### Skills (the fourteen nodes)
In the `<script>` block, search for `const SKILLS = [`.
Each entry is `{ n: 'Name', d: 'One-line description.' }`.
The order of this array is the node index used everywhere else —
if you add or remove a skill, update the connection list too.

### Skill connections (edges)
Right below SKILLS, search for `const E = [`.
Each pair `[a,b]` means "skill a is connected to skill b" using the
zero-based position in the SKILLS array (0 = first skill).
Each pair is stored once, smaller index first. Do not add a pair twice
and never connect a node to itself.

### Credentials
Search for `<ol class="creds">`. Each `<li class="cred">` is one entry,
oldest first. Edit the `<time datetime="YYYY-MM-DD">` date, the issuer,
the `<h3 class="cred-title">` title, and the `src` / `alt` of the image.
Certificate scans live in `assets/cert/`.

### Contact links
Search for `class="contact-grid"`. Each card is an `<a>` with its URL
in `href`. The footer statement link is `class="footer-cta"`.

## Deploying to GitHub Pages

1. Create a repository and push this folder's contents to its default branch.
2. In the repository: Settings → Pages → Source → "Deploy from a branch",
   choose the branch and the `/ (root)` folder.
3. The site appears at `https://<username>.github.io/<repo>/`.
4. If you change the canonical URL, update the `<link rel="canonical">`,
   the Open Graph URL, the JSON-LD `url`, and `sitemap.xml` to match.

After deploying, hard-refresh the page because older canvas scripts are
cached aggressively. (Ctrl+Shift+R on Windows/Linux, Cmd+Shift+R on macOS.)
