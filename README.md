# GitHub Pages Graph Template

Website Link Example: https://uhm-campus-energy.github.io/Github-Pages-Template/

A GitHub Pages (Jekyll) site that turns a CSV file into interactive graphs and tables.

## Guide to local set up
*Mac might not work perfectly I have windows so I can’t check sorry*
1. Install Ruby 3.3
Windows:
```winget install RubyInstallerTeam.RubyWithDevKit.3.3```
```$env:Path = "C:\Ruby33-x64\bin;" + $env:Path```
Mac:
```brew install ruby@3.3```
```echo 'export PATH="/opt/homebrew/opt/ruby@3.3/bin:$PATH"' >> ~/.zshrc```
```source ~/.zshrc```
2. Confirm version 3.3 with: 
```ruby -v```
3. Install more stuff
```gem install bundler```
```bundle install```
```bundle update github-pages```
4. Run locally
```bundle exec jekyll serve```

## General guide to setting up a github page site (if you’re curious)
https://docs.github.com/en/pages/setting-up-a-github-pages-site-with-jekyll/creating-a-github-pages-site-with-jekyll 

### If you aren’t using a github page template then you’ll need to install the template by entering these commands:
```gem install jekyll bundler```
Navigate to where the github page is stored locally (using cd “project_path”)
```jekyll new . --skip-bundle --force```
Edit the Gemfile
- Comment out: gem "jekyll", "~> 4.4.1" gem "minima", "~> 2.5"
- Uncomment: gem "github-pages", group: :jekyll_plugins
Edit the _config.yml file
- Change baseurl to name of repo
- Change url to https://[githubUsername].github.io
- You can change the other variables, up to you what to change it to tho

## Overview of Template

- **Summary** (`index.markdown`): total and top 10 items for a chosen period.
- **Period Comparison** (`Graphs/comparison.markdown`): monthly lines for several periods, all items combined.
- **Item Comparison** (`Graphs/item_comp.markdown`): monthly lines for several items in one period.
- Every graph has a "Download PNG with values" button, and every table has a "Download Excel" button.

## Using the Template

1. Click on `Use this template`, rename to whatever name you want
2. Edit the settings in `_config.yml`: `title`, `baseurl`, `url`, `data_file`, `value_label`, `value_unit` and `start_month`.
3. Put your data in a CSV with the columns `item`, `date` (as `YYYY-M-D`) and `value`. The sample is `data/sample.csv`.
5. Edit `about.markdown` and `_includes/footer.html`.
6. Preview locally with `bundle exec jekyll serve`, or push to GitHub and enable Pages.

To add a page, copy one in `Graphs/`, then link it from `_includes/quick-links.html`. The shared chart code is in `_includes/chart-common.html`.
