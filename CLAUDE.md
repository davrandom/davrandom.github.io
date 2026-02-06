# CLAUDE.md - AI Assistant Guide for davrandom.github.io

This document provides comprehensive guidance for AI assistants working with this codebase.

## Project Overview

This is a personal blog and portfolio website built with Jekyll and hosted on GitHub Pages. The site belongs to Davide Scaini and covers topics including programming, physics, acoustics, motorcycle travels, and DIY projects.

**Key Technologies:**
- Jekyll static site generator (GitHub Pages compatible)
- Ruby/Bundler for dependency management
- Kramdown for Markdown processing with GFM (GitHub Flavored Markdown) input
- Rouge for syntax highlighting
- Sass for CSS preprocessing
- Liquid templating engine

**Site URL:** davrandom.github.io

## Repository Structure

```
davrandom.github.io/
├── _config.yml              # Jekyll configuration (site settings, navigation, plugins)
├── Gemfile                  # Ruby dependencies (uses github-pages gem)
├── Gemfile.lock             # Locked dependency versions
├── _posts/                  # Blog posts (dated files: YYYY-MM-DD-title.{md,html})
│   └── en/                  # English language posts subdirectory
├── _drafts/                 # Draft posts (not published)
│   └── mydsmv_backup/       # Backup directory
├── _layouts/                # Page layouts
│   ├── default.html         # Base layout template
│   ├── post.html            # Blog post layout
│   ├── page.html            # Simple page layout
│   ├── page_w_picture.html  # Page layout with featured image
│   └── tag_index.html       # Tag archive page layout
├── _includes/               # Reusable components
│   ├── head.html            # HTML head section
│   ├── header.html          # Site header/navigation
│   ├── footer.html          # Site footer
│   ├── scripts.html         # JavaScript includes
│   ├── tagsforpost.html     # Tag display component
│   ├── disqus.html          # Comments integration
│   └── google_analytics.html # Analytics tracking
├── _sass/                   # Sass partials
│   ├── _base.scss           # Base styles
│   ├── _layout.scss         # Layout styles
│   └── _syntax-highlighting.scss # Code syntax highlighting
├── _plugins/                # Jekyll plugins (Ruby)
│   └── _tag_gen.rb          # Tag page generator
├── assets/                  # Static assets
│   ├── css/                 # Compiled CSS
│   ├── js/                  # JavaScript files
│   ├── img/                 # Image assets
│   └── scss/                # Additional Sass files
├── css/                     # Main CSS directory
├── images/                  # Site images (used in posts/pages)
├── index.html               # Homepage (recent posts with pagination)
├── about.md                 # About page
├── archive.md               # Post archive page
├── tag.md                   # Tags index page
├── moto.md                  # Motorcycle-related content page
├── loudspeakers.md          # Speaker/audio-related content page
├── feed.xml                 # RSS/Atom feed
├── config.rb                # Compass configuration (if used)
└── .github/
    └── dependabot.yml       # Automated dependency updates (Bundler)
```

## Development Workflow

### Local Development Setup

```bash
# Install dependencies
bundle install

# Build and serve locally (default port 4000)
bundle exec jekyll serve

# Build with drafts visible
bundle exec jekyll serve --drafts

# Build for production
bundle exec jekyll build
```

### Deployment

This is a GitHub Pages site. Deployment happens automatically when changes are pushed to the `master` branch. GitHub Pages builds and serves the site automatically.

## Working with Posts

### Post File Naming Convention

Posts MUST follow this naming pattern:
```
_posts/YYYY-MM-DD-title-with-hyphens.{md,html}
```

Examples:
- `_posts/2018-6-20-Use-tensorflow-to-calculate-gradients.md`
- `_posts/2016-08-03-Updated-gems-broken-jekyll.md`

### Post Front Matter

Required and common front matter fields:

```yaml
---
layout: post                  # REQUIRED: Use 'post' layout
title: Your Post Title        # REQUIRED: Post title
category: memo programming    # Optional: Space-separated categories
comments: true                # Optional: Enable Disqus comments (default: false)
image: filename.jpg           # Optional: Featured image (from /images/)
---
```

### Post Content Guidelines

1. **Markdown Format**: Use GitHub Flavored Markdown (GFM)
2. **Code Blocks**: Use fenced code blocks with language specifiers:
   ````markdown
   ```python
   # Your code here
   ```
   ````
3. **Images**: Reference images from `/images/` directory:
   ```markdown
   ![Alt text](/images/image-name.jpg)
   ```
4. **Internal Links**: Use site-relative paths with baseurl:
   ```liquid
   {{ site.baseurl }}/path/to/page/
   ```

### Drafts

- Place draft posts in `_drafts/` directory
- Drafts don't require dates in filename
- View drafts locally with `--drafts` flag
- Move to `_posts/` with proper date when ready to publish

## Working with Pages

### Page Types

1. **Simple Pages**: Use `layout: page` front matter
2. **Pages with Images**: Use `layout: page_w_picture` front matter

### Navigation

Navigation is configured in `_config.yml`:

```yaml
navigation:
 - title: Home
   url: /index.html
 - title: About
   url: /about/index.html
```

To add a new page to navigation, add it to this list.

## Styling & Assets

### Sass Architecture

- Partials in `_sass/` are imported into main stylesheets
- Use `_base.scss` for foundational styles
- Use `_layout.scss` for layout-specific styles
- Syntax highlighting styles in `_syntax-highlighting.scss`

### Adding Images

1. **Post/Page Images**: Place in `/images/` directory
2. **Asset Images**: Place in `/assets/img/` directory
3. Reference in posts/pages using absolute paths from root

### JavaScript

JavaScript files are in `/assets/js/` and included via `_includes/scripts.html`.

## Plugins & Custom Functionality

### Tag Generator Plugin

Location: `_plugins/_tag_gen.rb`

**What it does:**
- Automatically generates individual tag pages for all tags used in posts
- Creates pages at `/tag/[tag-name]/` for each unique tag
- Uses `tag_index.html` layout

**Configuration in _config.yml:**
```yaml
tag_page_layout: tag_page
tag_page_dir: tag
tag_permalink_style: pretty
```

**Usage in Posts:**
Tags are defined in front matter as space-separated categories or tags.

### Other Jekyll Plugins

Configured in `_config.yml`:
```yaml
plugins: [jekyll-paginate, jemoji]
paginate: 5
paginate_path: "blog/page:num/"
```

- **jekyll-paginate**: Enables pagination (5 posts per page)
- **jemoji**: Enables GitHub emoji support

## Building & Testing

### Before Committing Changes

1. **Build locally** to check for errors:
   ```bash
   bundle exec jekyll build
   ```

2. **Serve locally** to preview:
   ```bash
   bundle exec jekyll serve
   ```

3. **Check for common issues:**
   - Verify post filenames follow date convention
   - Ensure YAML front matter is valid
   - Check that all image references are correct
   - Test internal links

### Dependency Updates

Dependabot is configured to automatically update Bundler dependencies weekly. Review and merge Dependabot PRs regularly.

## Git Workflow

### Branch Strategy

- **master**: Production branch (auto-deploys to GitHub Pages)
- **claude/[task]-[id]**: Feature branches for AI assistant work

### Branch Naming Convention

When working as an AI assistant, use branches prefixed with `claude/`:
```
claude/add-new-post-XyZ123
claude/fix-styling-AbC456
claude/update-about-page-DeF789
```

### Commit Messages

Follow these conventions:
1. Use imperative mood ("Add feature" not "Added feature")
2. Keep first line under 70 characters
3. Include session URL at end:
   ```
   Add comprehensive CLAUDE.md documentation

   https://claude.ai/code/session_XXXXX
   ```

### Push Protocol

Always push to feature branches:
```bash
git push -u origin claude/branch-name
```

Never force push to master unless explicitly requested.

## Key Conventions for AI Assistants

### DO:

1. **Read existing posts** before creating new ones to match style and formatting
2. **Follow naming conventions** strictly for posts (YYYY-MM-DD-title.md)
3. **Test locally** before committing if possible
4. **Use proper front matter** with all required fields
5. **Reference the tag system** when creating posts with categories
6. **Maintain consistent markdown formatting** (GFM)
7. **Check for broken links** when modifying pages
8. **Update navigation** in _config.yml when adding new top-level pages
9. **Use existing layouts** rather than creating new ones
10. **Respect the multilingual structure** (English posts in _posts/en/)

### DON'T:

1. **Don't modify _config.yml** without explicit request
2. **Don't remove existing posts** without confirmation
3. **Don't change the site structure** (directory layout) without discussion
4. **Don't add new plugins** without verifying GitHub Pages compatibility
5. **Don't modify Gemfile** unless handling dependency updates
6. **Don't commit large binary files** (images > 1MB should be discussed)
7. **Don't break pagination** by removing paginate-related code
8. **Don't remove the Disqus integration** without explicit request
9. **Don't modify the tag generator plugin** unless fixing a bug
10. **Don't push directly to master** - use feature branches

### Code Style:

1. **HTML/Liquid**: 2-space indentation
2. **YAML**: 2-space indentation, use spaces not tabs
3. **Markdown**: Standard GFM formatting
4. **Ruby**: 4-space indentation (for plugins)
5. **Sass/CSS**: 2-space indentation

### Content Guidelines:

1. Posts are personal and technical in nature
2. Topics include: programming, physics, motorcycles, audio/acoustics, DIY
3. Mix of Italian and English content (recent posts tend to be English)
4. Code examples should be complete and runnable when possible
5. Technical accuracy is important - this is a scientist's blog

### Special Files to Note:

- **about.md**: Contains CV, publications, patents - keep updated carefully
- **moto.md**: Motorcycle-related content page
- **loudspeakers.md**: Audio/speaker projects page
- **feed.xml**: RSS feed - don't modify unless fixing feed issues

## Troubleshooting Common Issues

### Jekyll Won't Build

1. Check YAML front matter syntax (must have opening/closing `---`)
2. Verify post filename follows YYYY-MM-DD format
3. Check for liquid syntax errors in templates
4. Ensure all includes are properly closed

### Styling Not Appearing

1. Verify Sass files compile correctly
2. Check browser console for CSS loading errors
3. Ensure asset paths are correct (use `site.baseurl` when needed)

### Tags Not Generating

1. Verify `_tag_gen.rb` plugin is present and executable
2. Check that `tag_index.html` layout exists
3. Ensure tags are properly formatted in post front matter

### Pagination Not Working

1. Verify `jekyll-paginate` is in plugins list
2. Check `paginate` value in _config.yml
3. Ensure pagination code exists in index.html

## Additional Resources

- Jekyll Documentation: https://jekyllrb.com/docs/
- GitHub Pages Documentation: https://docs.github.com/en/pages
- Kramdown Syntax: https://kramdown.gettalong.org/syntax.html
- Liquid Template Language: https://shopify.github.io/liquid/

---

**Last Updated:** 2026-02-06
**Maintained for:** AI Assistant workflows with this repository
