# GitHub Pages Graph Template

A Jekyll-powered template that converts CSV datasets into interactive graphs and exportable data tables for GitHub Pages.

**[Live Preview & Demo Site](https://uhm-campus-energy.github.io/Github-Pages-Template/)**

---

## Quick Start & Setup

1. **Use This Template**  
   Click the **Use this template** button at the top of the repository to create your own copy.
   
2. **Configure `_config.yml`**  
   Update the following parameters to match your project:
   - `title`: Title of your site
   - `baseurl`: Repository name (e.g., `"/my-repo"`)
   - `url`: Your GitHub Pages URL (e.g., `"https://username.github.io"`)
   - `data_file`, `value_label`, `value_unit`, and `start_month`

3. **Prepare Your Data (You can skip if you want to create custom graphs)**  
   Add your CSV file to the repository. The data must include the following column headers:
   - `item`
   - `date` (`YYYY-M-D`)
   - `value`  
   *(See `data/sample.csv` for a working example).*

4. **Customize Content**  
   Edit `about.markdown` and `_includes/footer.html` with your project's custom text.

5. **Preview & Deploy**  
   Preview your site locally using `bundle exec jekyll serve`, or push to your `main` branch and enable **GitHub Pages** under repository settings.

> **Adding New Pages:** Copy any existing page in `Graphs/`, then link it inside `_includes/quick-links.html`. Shared chart rendering logic is located in `_includes/chart-common.html`.

---

## Local Development Guide

### 1. Install Ruby 3.3

#### Windows Setup
Open PowerShell as Administrator and run:
```powershell
winget install RubyInstallerTeam.RubyWithDevKit.3.3
$env:Path = "C:\Ruby33-x64\bin;" + $env:Path
```

#### MacOS Setup
Open Terminal and run (requires [Homebrew](https://brew.sh/)):
```zsh
brew install ruby@3.3
echo 'export PATH="/opt/homebrew/opt/ruby@3.3/bin:$PATH"' >> ~/.zshrc
source ~/.zshrc
```

---

### 2. Verify Installation
Check that Ruby 3.3 is active in your terminal:
```bash
ruby -v
```

---

### 3. Install Dependencies
Navigate to your local repository directory and run:
```bash
gem install bundler
bundle install
bundle update github-pages
```

---

### 4. Run Locally
Launch the Jekyll local development server:
```bash
bundle exec jekyll serve
```
Open `http://127.0.0.1:4000` in your web browser to preview your site.

---
## Template Overview

- Summary (index.markdown): total and top 10 items for a chosen period.
- Period Comparison (Graphs/comparison.markdown): monthly lines for several periods, all items combined.
- Item Comparison (Graphs/item_comp.markdown): monthly lines for several items in one period.
- Every graph has a "Download PNG with values" button, and every table has a "Download Excel" button.

*Every graph page includes a **"Download PNG with values"** button, and every table includes a **"Download Excel"** export button.*

---

## Creating a Jekyll Site From Scratch

If you are initializing a brand-new GitHub Pages project without using this pre-built template:

1. **Install Core Tools:**
   ```bash
   gem install jekyll bundler
   ```
2. **Initialize Site:**
   ```bash
   cd "your-project-path"
   jekyll new . --skip-bundle --force
   ```
3. **Update `Gemfile`:**
   ```ruby
   # Comment out standard gems:
   # gem "jekyll", "~> 4.4.1"
   # gem "minima", "~> 2.5"

   # Add GitHub Pages gem:
   gem "github-pages", group: :jekyll_plugins
   ```
4. **Update `_config.yml`:**
   ```yaml
   baseurl: "/repository-name"
   url: "https://username.github.io"
   ```
5. Refer to the official [GitHub Pages Jekyll Guide](https://docs.github.com/en/pages/setting-up-a-github-pages-site-with-jekyll/creating-a-github-pages-site-with-jekyll) for further details.
