# GitHub Actions Workflows

This directory contains automated workflows for maintaining and testing the site.

## Available Workflows

### 1. Update Dependencies (`update-dependencies.yml`)

**Purpose**: Automatically updates Ruby dependencies and creates pull requests.

**Triggers**:
- **Schedule**: Runs weekly on Mondays at 9:00 AM UTC
- **Manual**: Can be triggered from Actions tab with options for "all" or "security-only" updates

**What it does**:
1. Creates a new branch `dependencies/update-YYYY-MM-DD`
2. Updates dependencies in `Gemfile.lock`
3. Runs Jekyll build to test compatibility
4. Runs security audit on updated dependencies
5. Creates a pull request with changes and test results

**Benefits**:
- Keeps dependencies up-to-date automatically
- Fixes security vulnerabilities proactively
- Tests changes before creating PR
- Provides detailed change summary

**How to use manually**:
1. Go to [Actions tab](../../actions/workflows/update-dependencies.yml)
2. Click "Run workflow"
3. Select update type (all or security-only)
4. Click "Run workflow" button
5. Wait for PR to be created
6. Review and merge the PR

---

### 2. Jekyll Build Test (`jekyll-build-test.yml`)

**Purpose**: Tests that Jekyll builds successfully on every change.

**Triggers**:
- **Pull Requests**: Runs when PRs target the `master` branch
- **Push**: Runs on pushes to `master`
- **Manual**: Can be triggered from Actions tab

**What it does**:
1. Checks out the code
2. Installs Ruby and dependencies
3. Validates Jekyll configuration
4. Builds the site
5. Validates post front matter
6. Comments on PR with results

**Benefits**:
- Catches build errors before merging
- Validates post structure and front matter
- Provides immediate feedback on PRs
- Prevents broken deployments

---

### 3. Security Audit (`security-audit.yml`)

**Purpose**: Monitors dependencies for security vulnerabilities.

**Triggers**:
- **Schedule**: Runs daily at midnight UTC
- **Push**: Runs when `Gemfile` or `Gemfile.lock` changes on `master`
- **Manual**: Can be triggered from Actions tab

**What it does**:
1. Runs `bundler-audit` to check for known vulnerabilities
2. Creates/updates GitHub issues when vulnerabilities are found
3. Auto-closes issues when vulnerabilities are resolved
4. Uploads detailed audit results as artifacts

**Benefits**:
- Continuous security monitoring
- Automatic issue tracking
- Proactive vulnerability detection
- Historical audit records

**How to view results**:
1. Check the [Security tab](../../security) in the repository
2. Review automated issues labeled `security`
3. Download audit artifacts from workflow runs

---

## Workflow Dependencies

All workflows require:
- Ruby 3.2 (automatically installed)
- Bundler (included with Ruby)
- `github-pages` gem and dependencies

## Permissions

Workflows use these GitHub permissions:
- `contents: write` - To create branches and commits
- `pull-requests: write` - To create and comment on PRs
- `issues: write` - To create and manage security issues
- `security-events: write` - To report security findings

## Maintenance

### Updating Workflows

When modifying workflows:
1. Test changes in a fork or feature branch
2. Use `workflow_dispatch` to manually test
3. Monitor first few automated runs
4. Document changes in this README

### Disabling Workflows

To temporarily disable a workflow:
1. Go to Actions tab
2. Click on the workflow name
3. Click "..." menu → "Disable workflow"

### Schedule Changes

Current schedules:
- **Dependency Updates**: Mondays at 9:00 AM UTC
- **Security Audit**: Daily at midnight UTC

To change schedules, edit the `cron` expressions in the workflow files.

## Troubleshooting

### Workflow fails on bundle install

**Solution**: Check if `Gemfile` or `Gemfile.lock` has syntax errors or incompatible version constraints.

### PR creation fails

**Solution**: Ensure the `GITHUB_TOKEN` has necessary permissions. Check repository settings → Actions → General → Workflow permissions.

### Build fails but works locally

**Solution**: May be environment differences. Check Ruby version matches local setup (currently 3.2).

### Security audit creates too many issues

**Solution**: Adjust the schedule or set up issue auto-closing rules in the workflow.

## Best Practices

1. **Review automated PRs promptly** - Don't let dependency updates pile up
2. **Test locally when uncertain** - Clone the branch and test before merging
3. **Monitor workflow runs** - Check Actions tab weekly for failures
4. **Keep workflows updated** - Update action versions when GitHub suggests
5. **Document workflow changes** - Update this README when modifying workflows

## Additional Resources

- [GitHub Actions Documentation](https://docs.github.com/en/actions)
- [Jekyll CI Documentation](https://jekyllrb.com/docs/continuous-integration/)
- [Bundler Audit](https://github.com/rubysec/bundler-audit)
- [Repository Security Guide](../SECURITY_UPDATE_GUIDE.md)

---

**Last Updated**: 2026-02-06
