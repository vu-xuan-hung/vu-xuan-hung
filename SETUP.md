# Setup — Vu Xuan Hung GitHub Metrics Profile

This version intentionally follows the style of the `lowlighter/metrics`
showcase: one large data-driven dashboard instead of many separate stat cards.

It is configured for:

- GitHub username: `vu-xuan-hung`
- Profile repository: `vu-xuan-hung/vu-xuan-hung`
- Timezone: `Asia/Ho_Chi_Minh`

## Files

Copy these two files into the profile repository:

```text
README.md
.github/workflows/metrics.yml
```

## 1. Create METRICS_TOKEN

Open GitHub:

```text
Settings
→ Developer settings
→ Personal access tokens
→ Tokens (classic)
→ Generate new token (classic)
```

For public GitHub metrics, a classic PAT without extra repository scopes is
normally sufficient. If later you intentionally want metrics from private
repositories, grant only the additional access you actually need.

Copy the token.

## 2. Add it as a repository secret

Open:

```text
vu-xuan-hung/vu-xuan-hung
→ Settings
→ Secrets and variables
→ Actions
→ New repository secret
```

Create:

```text
Name: METRICS_TOKEN
Secret: <your PAT>
```

Never put the token directly in README.md or metrics.yml.

## 3. Commit

From the profile repository:

```bat
git add README.md .github\workflows\metrics.yml
git commit -m "feat: redesign profile with GitHub metrics"
git push
```

## 4. Generate the dashboard

On GitHub:

```text
Actions
→ GitHub Metrics
→ Run workflow
```

The action will create:

```text
github-metrics.svg
```

and commit it to `main`. The README automatically displays that SVG.

## Included in this version

The dashboard dynamically shows GitHub-derived information such as:

- profile/repository statistics
- recent GitHub activity
- contribution information
- isometric contribution calendar
- coding time/day habits
- most-used languages

The README separately highlights the technical direction you asked for:

- AI Agents
- RAG
- Machine Learning / Deep Learning
- Computer Vision
- Docker
- Algorithms / Optimization
- ACO / PSO

## Note about private repositories

Metrics only reflect information the configured token can access. Do not grant
private-repository access just to make the profile look busier.
