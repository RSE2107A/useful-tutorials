# 📘 Create a Markdown Documentation Site with MkDocs

MkDocs is a static site generator that builds websites from Markdown files. It’s fast, simple, and ideal for technical documentation.

---

## 🚀 Step 1: Install MkDocs

### ✅ Requirements

- Python 3.6+
- pip (Python package manager)

### 🔧 Installation

```bash
pip install mkdocs
```

🧪 Verify installation:

```bash
mkdocs --version
```

---

## 🏗️ Step 2: Create a New MkDocs Project

```bash
mkdocs new my-docs-site
cd my-docs-site
```

📁 This creates a basic folder structure:

```
my-docs-site/
├── docs/
│   └── index.md
└── mkdocs.yml
```

* `docs/`: All your Markdown files go here.
* `mkdocs.yml`: Configures your site.

---

## ✍️ Step 3: Add Your Markdown Files

Add or edit files in the `docs/` folder.

Example:

```bash
cd docs
touch getting-started.md
touch ssh-tutorial.md
```

Edit them with any Markdown editor.

---

## 🧭 Step 4: Configure the Site Navigation

Edit `mkdocs.yml`:

```yaml
site_name: My Docs Site

nav:
  - Home: index.md
  - Getting Started: getting-started.md
  - SSH Tutorial: ssh-tutorial.md
```

This defines the navigation menu.

---

## 👀 Step 5: Preview Your Site Locally

Run the built-in development server:

```bash
mkdocs serve
```

Then visit: [http://127.0.0.1:8000](http://127.0.0.1:8000)

🌀 Live reload is supported — changes are automatically refreshed.

---

## 🏁 Step 6: Build the Static Site

```bash
mkdocs build
```

This creates a `site/` directory with static HTML files.

---

## 🌐 Step 7: Deploy Your Site

### GitHub Pages (recommended for free hosting)

```bash
mkdocs gh-deploy
```

* Pushes `site/` to the `gh-pages` branch of your repo.
* Make sure your project is in a GitHub repository.

---

## 🎨 Optional: Use a Custom Theme

Install the **Material for MkDocs** theme:

```bash
pip install mkdocs-material
```

Update `mkdocs.yml`:

```yaml
theme:
  name: material
```

---

## 📁 Folder Summary

```
my-docs-site/
├── docs/
│   ├── index.md
│   ├── getting-started.md
│   └── ssh-tutorial.md
├── mkdocs.yml
└── site/         ← built files (auto-generated)
```

---

## 🧹 Clean Up Build

If needed:

```bash
mkdocs clean
```


