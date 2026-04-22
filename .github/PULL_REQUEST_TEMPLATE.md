# Pull Request: OS2 AI Heat Control - Hugo Migration Complete

## Summary

Branch #8 completes the migration of the OS2 AI Heat Control website from a Lovable/TypeScript-based setup to Hugo, with all content now editable as simple markdown files.

### What this PR does:
- Migrates from Lovable/TypeScript to Hugo static site generator
- All text content is now in markdown (`docs/content/_index.md`)
- Creates reusable shortcodes for cards and diagrams
- Adds the datamodel SVG diagram replacing the table
- Includes GitHub Actions workflow for automatic deployment
- Cleans up orphaned code from earlier iterations

### Changes include:
- `docs/layouts/` - Hugo layout templates
- `docs/content/_index.md` - All page content
- `docs/layouts/shortcodes/` - Card, cards, diagram shortcodes
- `docs/static/` - CSS, images, SVG diagrams
- `.github/workflows/hugo.yaml` - CI/CD for GitHub Pages

---

## How to Test Locally

### Prerequisites

**Required:** [Podman](https://podman.io)

For installation guides, see:
- **macOS:** https://podman.io/ins allation/macos
- **Windows:** https://podman.io/installation/windows
- **Linux:** https://podman.io/installation/linux

### Start the Site

```bash
# Start the test environment
podman play kube test-env.yaml

# The site is now available at
http://localhost:4321

# To stop when done
podman kube down test-env.yaml
```

---

## Deployment

When this PR is merged to `main`:

1. **GitHub Actions** will automatically build the site
2. Go to **Settings → Pages** in the repository
3. Ensure "Source" is set to **GitHub Actions**
4. The live URL will be shown in the Actions run output

### Manual build (if needed)

```bash
# Install Hugo
brew install hugo  # macOS
choco install hugo -y  # Windows
apt install hugo  # Linux

# Build
hugo --minify

# Output is in docs/public/
```

---

## File Structure

```
.
├── .github/
│   └── workflows/
│       └── hugo.yaml          # CI/CD workflow
├── .dev/
│   └── plan.md               # Project plan
├── docs/
│   ├── config.yaml          # Hugo config
│   ├── content/
│   │   └── _index.md         # All page content
│   ├── layouts/
│   │   ├── index.html        # Main layout
│   │   └── shortcodes/
│   │       ├── card.html     # Card component
│   │       ├── cards.html    # Card grid wrapper
│   │       └── diagram.html  # Image shortcode
│   └── static/
│       ├── style.css         # All styling
│       ├── os2-logo.png     # Logo
│       ├── hero-illustration.svg
│       └── datamodel-diagram.svg
├── test-env.yaml             # Podman test environment
└── README.md
```

---

## Making Content Changes

Edit `docs/content/_index.md` and push. The site rebuilds automatically.

### Shortcodes available:

```markdown
# Single card
{{< card title="Title" icon="wrench" >}}
Card content here
{{< /card >}}

# Card grid
{{< cards >}}
{{< card >}}...{{< /card >}}
{{< /cards >}}

# Diagram
{{< diagram src="/image.svg" alt=" Description" >}}
```

### Available icons:
- database, cog, cable, shield, wrench, headset, brain, chart, users, building

---

## Known Limitations

1. **No expandable cards** - The original expand/collapse functionality is disabled. See `.dev/plan.md` Phase 11 for future work.
2. **No animations** - Scroll-reveal effects not implemented (optional future work).