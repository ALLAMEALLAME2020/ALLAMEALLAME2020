# GitHub Profile Setup Guide

This guide will help you set up your GitHub profile README with all the features.

## Quick Setup

1. Create a repository with the same name as your GitHub username: `ALLAMEALLAME2020`
2. Add the `README.md` file to this repository
3. Commit and push - your profile will update automatically!

## Optional: Snake Animation

To add the contribution snake animation:

### Step 1: Create Workflow File

Create `.github/workflows/snake.yml` in your profile repository:

\`\`\`yaml
name: Generate Snake

on:
  schedule:
    - cron: "0 */12 * * *"
  workflow_dispatch:

jobs:
  build:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v3
      
      - uses: Platane/snk@v3
        with:
          github_user_name: ALLAMEALLAME2020
          outputs: |
            dist/github-snake.svg
            dist/github-snake-dark.svg?palette=github-dark
            
      - uses: crazy-max/ghaction-github-pages@v3.1.0
        with:
          target_branch: output
          build_dir: dist
        env:
          GITHUB_TOKEN: ${{ secrets.GITHUB_TOKEN }}
\`\`\`

### Step 2: Enable GitHub Actions

1. Go to your repository Settings
2. Navigate to Actions → General
3. Enable "Read and write permissions"
4. Save changes

### Step 3: Add Snake to README

Add this to your README.md where you want the snake to appear:

\`\`\`markdown
<div align="center">

<img src="https://raw.githubusercontent.com/ALLAMEALLAME2020/ALLAMEALLAME2020/output/github-snake-dark.svg" alt="Snake animation" />

</div>
\`\`\`

### Step 4: Trigger First Run

1. Go to Actions tab in your repository
2. Click "Generate Snake" workflow
3. Click "Run workflow"
4. Wait for it to complete

The snake will now update automatically every 12 hours!

## Customization Tips

### Change Theme Colors

All stats use the GitHub dark theme with blue accents. To change colors, modify the URL parameters:

- `bg_color` - Background color
- `title_color` - Title text color
- `text_color` - Body text color
- `icon_color` - Icon color

Example:
\`\`\`
?theme=dark&bg_color=0d1117&title_color=58a6ff
\`\`\`

### Update Social Links

Replace the Instagram and Discord links with your actual profile URLs:

\`\`\`markdown
[![Instagram](https://img.shields.io/badge/Instagram-E4405F?style=for-the-badge&logo=instagram&logoColor=white)](YOUR_INSTAGRAM_URL)
[![Discord](https://img.shields.io/badge/Discord-5865F2?style=for-the-badge&logo=discord&logoColor=white)](YOUR_DISCORD_URL)
\`\`\`

### Add More Badges

Visit [shields.io](https://shields.io) to create custom badges for any technology or platform.

## Troubleshooting

**Stats not showing?**
- Make sure your repository is public
- Check that your username is spelled correctly
- Wait a few minutes for GitHub's cache to update

**Snake not generating?**
- Verify GitHub Actions are enabled
- Check that workflow file is in `.github/workflows/` directory
- Ensure you have write permissions enabled

**Profile not updating?**
- Repository name must match your username exactly
- README.md must be in the root directory
- Changes may take a few minutes to appear

---

Need help? Open an issue or reach out on Discord!
