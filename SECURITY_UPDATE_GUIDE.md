# Security Update Guide

## Current Vulnerability Status

GitHub has detected **11 vulnerabilities** in this repository's dependencies:
- **1 High severity**
- **9 Moderate severity**
- **1 Low severity**

## Identified Vulnerable Dependencies

Based on the current `Gemfile.lock` (github-pages 227), the following dependencies are outdated and have known vulnerabilities:

### Critical Updates Needed

1. **nokogiri** (Currently: 1.13.9)
   - Multiple CVEs related to XML parsing vulnerabilities
   - **Fix**: Update to >= 1.16.0
   - **Severity**: HIGH

2. **activesupport** (Currently: 6.0.5.1)
   - Potential security issues with older Rails components
   - **Fix**: Update to >= 7.0.8.6
   - **Severity**: MODERATE

3. **rexml** (Currently: 3.2.5)
   - XML parsing vulnerabilities (DoS attacks)
   - **Fix**: Update to >= 3.3.9
   - **Severity**: MODERATE

4. **kramdown** (Currently: 2.3.2)
   - Potential XSS vulnerabilities in markdown processing
   - **Fix**: Update to >= 2.4.0
   - **Severity**: MODERATE

5. **addressable** (Currently: 2.8.0)
   - ReDoS vulnerability in URI parsing
   - **Fix**: Update to >= 2.8.1
   - **Severity**: MODERATE

6. **commonmarker** (Currently: 0.23.7)
   - Multiple security issues in markdown parsing
   - **Fix**: Update to >= 0.23.10
   - **Severity**: MODERATE

7. **github-pages** (Currently: 227)
   - Outdated meta-package containing vulnerable dependencies
   - **Fix**: Update to >= 232 (or latest)
   - **Severity**: Various (indirect)

## How to Fix Vulnerabilities

### Method 1: Automatic Update (Recommended)

1. **Update the Gemfile** (already done in latest commit):
   ```ruby
   source 'https://rubygems.org'

   gem 'github-pages', '~> 232', group: :jekyll_plugins

   # Security updates
   gem 'nokogiri', '>= 1.16.0'
   gem 'activesupport', '>= 7.0.8.6'
   gem 'rexml', '>= 3.3.9'
   ```

2. **Run bundle update**:
   ```bash
   bundle update
   ```

3. **Test the site locally**:
   ```bash
   bundle exec jekyll serve
   ```

4. **Commit the updated Gemfile.lock**:
   ```bash
   git add Gemfile Gemfile.lock
   git commit -m "Update dependencies to fix security vulnerabilities"
   git push
   ```

### Method 2: Use Dependabot (Automated)

Dependabot is already configured in `.github/dependabot.yml`. It will:
- Automatically detect vulnerable dependencies
- Create pull requests with updates weekly
- Test compatibility before merging

**Action required**: Review and merge Dependabot PRs regularly.

### Method 3: Manual Gemfile.lock Update

If you can't run `bundle update` locally, you can:

1. Push the updated `Gemfile` to GitHub
2. Let GitHub Actions or Dependabot regenerate the lockfile
3. Pull the changes back

## Verification

After updating, verify the fixes:

```bash
# Check for vulnerabilities (if using bundler-audit)
bundle audit check --update

# Test the Jekyll build
bundle exec jekyll build

# Serve locally to test
bundle exec jekyll serve
```

## GitHub Pages Compatibility

**Important**: GitHub Pages only supports specific versions of gems. Always verify compatibility:

1. Check current supported versions:
   https://pages.github.com/versions/

2. The `github-pages` gem is a meta-package that ensures all dependencies are GitHub Pages compatible

3. After updating, monitor your GitHub Pages build status for any deployment failures

## Known Issues with Current Setup

### Issue 1: Dynamic Version Fetching (Original Gemfile)

The original Gemfile tried to fetch versions dynamically:

```ruby
require 'json'
require 'open-uri'
versions = JSON.parse(open('https://pages.github.com/versions.json').read)
gem 'github-pages', versions['github-pages']
```

**Problems**:
- Fails in restricted network environments
- Non-deterministic builds (version can change between runs)
- Security risk (remote code execution potential)

**Solution**: Use pinned versions as shown in Method 1 above.

### Issue 2: Outdated Dependencies

The lockfile hasn't been updated since github-pages version 227 (circa 2022), which is significantly outdated.

**Solution**: Run `bundle update` regularly (at least monthly).

## Post-Update Checklist

After updating dependencies:

- [ ] Run `bundle exec jekyll build` successfully
- [ ] Test site locally with `bundle exec jekyll serve`
- [ ] Check all blog posts render correctly
- [ ] Verify tag pages work (custom plugin compatibility)
- [ ] Test markdown rendering and code syntax highlighting
- [ ] Check that pagination works
- [ ] Verify images and assets load correctly
- [ ] Push changes and confirm GitHub Pages builds successfully

## Monitoring

To stay updated on vulnerabilities:

1. **Enable GitHub Security Alerts**:
   - Go to Settings → Security & analysis
   - Enable "Dependabot alerts"
   - Enable "Dependabot security updates"

2. **Weekly Checks**:
   - Review Dependabot PRs
   - Check GitHub Security tab
   - Run `bundle audit` locally

3. **Subscribe to Security Advisories**:
   - Watch the repositories of critical dependencies
   - Follow Ruby security mailing lists

## Additional Security Recommendations

1. **Pin Major Versions**: Use `~>` version specifiers to allow patch updates but prevent breaking changes

2. **Regular Updates**: Update dependencies at least monthly, even without security alerts

3. **Test Before Deploy**: Always test updated dependencies locally before pushing

4. **Automated CI/CD**: Consider adding GitHub Actions to:
   - Run tests on every push
   - Build Jekyll site to catch errors
   - Run security audits automatically

5. **Review Custom Code**: The `_tag_gen.rb` plugin should be reviewed for security issues

## Resources

- GitHub Security Advisory Database: https://github.com/advisories
- Ruby Security Advisories: https://github.com/rubysec/ruby-advisory-db
- Bundler Audit: https://github.com/rubysec/bundler-audit
- GitHub Pages Versions: https://pages.github.com/versions/
- Jekyll Security: https://jekyllrb.com/docs/security/

---

**Last Updated**: 2026-02-06
**Next Review**: 2026-03-06 (Monthly)

## Quick Reference: Update Commands

```bash
# Update all dependencies
bundle update

# Update specific gem
bundle update <gem-name>

# Check for vulnerabilities
gem install bundler-audit
bundle audit check --update

# Update github-pages meta-package
bundle update github-pages

# Clean and rebuild
bundle clean --force
bundle install
```
