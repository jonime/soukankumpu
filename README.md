# Soukankumpu

Tools for the Soukankumpu housing company. Each tool lives in its own directory.

## Parking

The [parking tool](parking/index.html) contains two interactive parking maps. Click a space to switch between reserved and guest parking. Selections are saved in the current browser's localStorage, not shared between users or devices.

The page and its SVG assets live together in `parking/`, so their relative links work locally and on GitHub Pages. When serving the repository root locally, open `http://127.0.0.1:8765/parking/`.

## GitHub Pages

1. Create an empty GitHub repository named `soukankumpu`. Use a public repository, or a GitHub plan that supports Pages for private repositories.
2. In the repository, open **Settings > Pages** and select **GitHub Actions** as the source.
3. Connect this local repository and push its first commit, replacing `YOUR_USERNAME` below:

```sh
git add -A
git commit -m "Add parking maps and GitHub Pages deployment"
git remote add origin https://github.com/YOUR_USERNAME/soukankumpu.git
git push -u origin main
```

Every subsequent push to `main` deploys automatically. Check the **Actions** tab for the deployment result and published URL. You can also run **Deploy to GitHub Pages** manually using **Run workflow**.

The parking page address is `https://YOUR_USERNAME.github.io/soukankumpu/parking/`. No `gh-pages` branch is required. If the first deployment ran before Pages was enabled, enable it and rerun the workflow.

The workflow publishes the `parking/` directory, preserving its path. For future tools, add their directories to the workflow's **Prepare static site** copy step. The repository root is available for a future tool index page.

Selections from the local development URL do not transfer to the GitHub Pages URL. Set them again on the published site. Clearing browser storage also clears the selections.
