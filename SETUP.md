# GitHub Metrics Profile Setup

This folder is meant to become the special GitHub profile repository for the account `ashburn2k`.

## What this installs

- A profile `README.md` that displays `/github-metrics.svg`
- A GitHub Actions workflow at `.github/workflows/metrics.yml`
- A daily scheduled run using `lowlighter/metrics@latest`
- A manual `workflow_dispatch` trigger so the metrics can be generated immediately

## Finish setup

1. Create or open a public GitHub repository named exactly like your GitHub username.

   For the current scaffold, that repo is:

   ```text
   ashburn2k/ashburn2k
   ```

2. Create a GitHub personal access token for Metrics.

   Recommended secret name:

   ```text
   METRICS_TOKEN
   ```

   For public profile metrics, start with the least access that works for your selected plugins. The base metrics in this scaffold need repository read access and the workflow needs permission to write the generated SVG back to the profile repository.

3. Add the token as a repository secret:

   ```text
   Settings -> Secrets and variables -> Actions -> New repository secret
   ```

4. Push this folder to your profile repository:

   ```zsh
   git init
   git branch -M main
   git add README.md SETUP.md .github/workflows/metrics.yml
   git commit -m "Install GitHub profile metrics"
   git remote add origin https://github.com/ashburn2k/ashburn2k.git
   git push -u origin main
   ```

5. In GitHub, open:

   ```text
   Actions -> Metrics -> Run workflow
   ```

   The first successful run should commit `github-metrics.svg` into the repository.

## If your GitHub login is not `ashburn2k`

Change both of these before pushing:

- Repository remote: `https://github.com/YOUR_LOGIN/YOUR_LOGIN.git`
- Workflow input in `.github/workflows/metrics.yml`: `user: YOUR_LOGIN`
