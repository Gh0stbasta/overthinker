# Overthinker Archive
Jekyll-based German overthinking archive website using the Cayman theme. This repository hosts a personal collection of ideas that escalated into endless thought spirals.

Always reference these instructions first and fallback to search or bash commands only when you encounter unexpected information that does not match the info here.

## Working Effectively
- Bootstrap and setup the repository:
  - Ruby 3.2.3+ is required and typically pre-installed
  - `sudo gem install jekyll bundler` -- installs Jekyll and Bundler (takes 30-60 seconds)
  - `sudo gem install jekyll-theme-cayman` -- installs the required theme (takes 10-30 seconds)
- Build the site:
  - `jekyll clean` -- cleans previous build artifacts (takes <1 second)
  - `jekyll build` -- builds the static site (takes <1 second). Build artifacts go in `_site/`
- Serve locally for testing:
  - `jekyll serve --host 0.0.0.0 --port 4000` -- serves site locally on port 4000
  - Test with: `curl -s http://localhost:4000` to verify it's responding
  - Stop server with Ctrl+C

## Content Structure and Creation
- Content is organized in `/entries/[topic-name]/` directories
- Each entry should contain:
  - `idea.md` -- the original harmless idea
  - `notes.md` -- the overthinking spiral that followed
  - `sketches/` -- optional directory for visual representations
- Example structure:
  ```
  entries/
    der-perfekte-kaffeebecher/
      idea.md
      notes.md
      sketches/
        diagram1.png
  ```
- Create new entries: `mkdir -p entries/new-topic/{sketches}`

## Validation
- Always manually validate any changes by building and serving the site locally
- ALWAYS run through a complete scenario after making changes:
  1. `jekyll clean && jekyll build` to rebuild from scratch
  2. `jekyll serve --host 0.0.0.0 --port 4000` to serve locally
  3. Test with `curl -s http://localhost:4000 | head -10` to verify HTML output
  4. Navigate to created entries to ensure they appear correctly
- All build commands complete in under 1 second - if they take longer, something is wrong
- Always clean build artifacts before committing: `jekyll clean`

## Common Commands Output Reference
The following are outputs from frequently run commands. Reference them instead of running bash commands to save time.

### Repository root structure
```
ls -la
.
..
.git/
.github/
.gitignore
README.md
_config.yml
index.md
entries/
```

### Dependencies and versions
```
ruby --version
ruby 3.2.3 (2024-01-18 revision 52bb2ac0a6) [x86_64-linux-gnu]

gem list jekyll
jekyll (4.4.1)
jekyll-sass-converter (3.1.0)
jekyll-seo-tag (2.8.0)
jekyll-theme-cayman (0.2.0)
jekyll-watch (2.2.1)
```

### Build timing expectations
```
time jekyll clean
real    0m0.326s
user    0m0.248s
sys     0m0.078s

time jekyll build
real    0m0.403s
user    0m0.317s
sys     0m0.091s
```

## Configuration Files

### _config.yml
```yaml
theme: jekyll-theme-cayman
markdown: kramdown
```

### Main content files
- `README.md` -- German documentation about the repository concept
- `index.md` -- Homepage with front matter layout: default
- Jekyll automatically generates navigation and styling from the theme

## Troubleshooting
- If Jekyll is not found: Run `sudo gem install jekyll bundler`
- If theme errors occur: Run `sudo gem install jekyll-theme-cayman`
- If build fails: Run `jekyll clean` first, then `jekyll build`
- If serve command fails: Ensure port 4000 is available or change port with `--port 4001`
- Permission errors with gem install: Always use `sudo gem install` on this system

## Important Notes
- This is a personal overthinking archive, content is in German
- The site uses Jekyll's automatic Markdown processing
- No complex build process or CI/CD - just static Jekyll generation
- Theme generates deprecation warnings about Sass imports - these are harmless
- Always exclude `_site/`, `.jekyll-cache/`, and `.sass-cache/` from version control
- Build artifacts should never be committed to the repository