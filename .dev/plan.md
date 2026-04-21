# OS2 AI Heat Control - Hugo Migration Plan

## Overview
Migrate the existing Lovable-based website (https://os2aiheatcontrol.4bc.dk/) to Hugo, with all content editable as simple markdown files.

## Goals
- 1:1 replication of UX and visual design from original site
- All text content in markdown files
- Test locally using Podman
- Deploy to GitHub Pages for production

## Components

### Core Technologies
- **Hugo** - Static site generator (using `klakegg/hugo:latest` image)
- **Podman** - Container runtime for local testing  
- **Markdown** - Content format for all editable text
- **GitHub Pages** - Production hosting

### Hugo Shortcodes Reference
See: https://gohugo.io/content-management/shortcodes/

Shortcodes go in `layouts/shortcodes/` and are called with:
- `{{< name >}}` (standard) or `{{% name %}}` (markdown)
- Named args: `{{< card title="Foo" >}}`
- Content: `{{< card >}}content{{< /card >}}`
- Inner content processed with: `{{ .Inner | markdownify }}`

---

## Implementation Phases (Completed)

### Phase 1: Basic Hugo Setup ✓
- [x] Clean slate (docs folder deleted)
- [x] Create minimal config.yaml
- [x] Create basic index.html layout
- [x] Test: Podman serves page

### Phase 2: Content Structure ✓
- [x] Create content/_index.md with all text sections
- [x] Add navbar and footer to layout
- [x] Test: All text sections visible

### Phase 3: Styling ✓
- [x] Create static/style.css
- [x] OS2 color palette (dusty blue #88B0D8, mint #C0D0D8)
- [x] Inter font
- [x] Fixed navbar
- [x] Hero with background blur orbs
- [x] Test: Visual match to original

### Phase 4: Assets - Logo & Hero ✓
- [x] Add os2-logo.png to navbar
- [x] Create hero illustration SVG
- [x] Add to layout (hero should be left-aligned with diagram on right)
- [x] Test: Assets display correctly

### Phase 5: Card Shortcodes ✓
- [x] Create `layouts/shortcodes/card.html` - card with title and optional icon
- [x] Create `layouts/shortcodes/cards.html` - wrapper for grid layout
- [x] Create `layouts/shortcodes/diagram.html` - img shortcode
- [x] Update content/_index.md to use shortcodes

### Phase 6: Typography & Layout Fixes ✓
- [x] Font: 'Inter', 'Source Sans 3', Arial, sans-serif
- [x] Font weights: 300, 400, 500, 600, 700
- [x] Container width: 720px
- [x] Content-section padding: 120px vertical
- [x] h2 margin: 120px between sections

### Phase 7: SVG Diagrams ✓
- [x] DataModelDiagram.tsx → static/datamodel-diagram.svg

### Phase 8: Cleanup ✓
- [x] Remove orphaned card-expanded shortcode
- [x] Remove dead .card p CSS selector

---

## Remaining Work

### Phase 9: SVG Diagrams (Future)
- [ ] ArchitectureDiagram.tsx → static/diagram-architecture.svg  
- [ ] RelationshipGraph.tsx → static/diagram-relationships.svg
- [ ] StandardAnalogySection.tsx → static/diagram-analogy.svg

### Phase 10: Animations (Optional)
- [ ] Scroll-reveal effects

### Phase 11: Expandable Cards (Postponed)
- Accordion/expand functionality not working reliably in Hugo
- Options for future:
  1. Use native `<details>/<summary>` HTML
  2. Use external JS file with event listeners
  3. Accept static cards without expand

---

## GitHub Pages Deployment

### Prerequisites
- Repository must be on GitHub (can be private or public)
- GitHub Actions enabled (Settings → Actions → General → Allow all actions)

### Step 1: Configure GitHub Actions
Create `.github/workflows/hugo.yaml`:

```yaml
name: Deploy to GitHub Pages

on:
  push:
    branches:
      - main  # Set a branch to deploy

jobs:
  deploy:
    runs-on: ubuntu-latest
    permissions:
      contents: write
    concurrency:
      group: ${{ github.workflow }}-${{ github.ref }}
    steps:
      - uses: actions/checkout@v4
        with:
          submodules: true  # Fetch Hugo themes (true if recursive)
          fetch-depth: 0    # Fetch all history for .GitInfo

      - name: Setup Hugo
        uses: peaceiris/actions-hugo@v2
        with:
          hugo-version: 'latest'
          extended: true

      - name: Build
        run: hugo --minify

      - name: Deploy
        uses: peaceiris/actions-gh-pages@v4
        with:
          github_token: ${{ secrets.GITHUB_TOKEN }}
          publish_dir: ./docs/public
```

### Step 2: Enable GitHub Pages
1. Go to **Settings → Pages**
2. Source: **Deploy from a branch**
3. Branch: **gh-pages**
4. Folder: **/(root)**
5. Click **Save**

### Step 3: Push to GitHub
```bash
git add .
git commit -m "feat: complete Hugo migration with GitHub Pages"
git push origin main
```

### Step 4: Verify
- Go to **Settings → Pages**
- Check "GitHub Pages" section for live URL
- Build takes 1-2 minutes

---

## Testing Locally

### Start local server
```bash
podman play kube test-env.yaml

# Access at
http://localhost:4321

# Stop server
podman kube down test-env.yaml
```

---

## Component Mapping

| TS Component | Hugo Implementation |
|--------------|-----------------|
| Navbar.tsx | ✓ In layout |
| HeroSection.tsx | ✓ In layout |
| HeroIllustration.tsx | ✓ In layout (SVG) |
| IntroSection.tsx | ✓ In markdown |
| GrundelementerSection.tsx | ✓ card shortcode (static) |
| VendorSection.tsx | ✓ card shortcode |
| GovernanceSection.tsx | ✓ card shortcode |
| DataModelDiagram.tsx | ✓ datamodel-diagram.svg |
| FooterSection.tsx | ✓ In layout |

---

## Icon Mapping (lucide-react → shortcode)

| TS Icon Name | Shortcode name |
|--------------|----------------|
| Database | database |
| Cog | cog |
| Cable | cable |
| ShieldCheck | shield |
| Wrench | wrench |
| HeadsetIcon | headset |
| BrainCircuit | brain |
| BarChart3 | chart |
| Users | users |
| Building2 | building |

---

## Excluded from Repo
- `/docs/public/` - Hugo generated output
- `/.dev/` - Local development files