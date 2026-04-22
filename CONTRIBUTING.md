# Contributing to OS2 AI Heat Control

## Development

### Prerequisites

- [Podman](https://podman.io)

For installation:
- **macOS:** https://podman.io/installation/macos
- **Windows:** https://podman.io/installation/windows
- **Linux:** https://podman.io/installation/linux

### Local Development

```bash
# Start the test environment
podman play kube test-env.yaml

# The site is available at
http://localhost:4321

# Stop when done
podman kube down test-env.yaml
```

### Building Manually

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

## Making Content Changes

All content is in `docs/content/_index.md`. Edit and push - the site rebuilds automatically via GitHub Actions.

### Shortcodes

```markdown
# Single card
{{< card title="Title" icon="wrench" >}}
Card content
{{< /card >}}

# Card grid
{{< cards >}}
{{< card >}}...{{< /card >}}
{{< /cards >}}

# Diagram
{{< diagram src="/image.svg" alt="Description" >}}
```

### Available Icons
database, cog, cable, shield, wrench, headset, brain, chart, users, building

---

## Deployment

When changes are merged to `main`:
1. GitHub Actions builds automatically
2. Go to **Settings → Pages** → Source: **GitHub Actions**
3. Live URL shown in Actions output