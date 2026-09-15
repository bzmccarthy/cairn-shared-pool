# Cairn Shared Pool — GitHub Pages edition

Ready-to-host files for an Owlbear Rodeo extension. Players contribute dice; the GM rolls the pool and everyone sees the same highest result.

## Install

1. Create a PUBLIC GitHub repository named exactly `cairn-shared-pool`. Enable Add README when creating it.
2. Use Add file > Upload files. Upload the CONTENTS of this extracted folder (index.html, manifest.json, icon.svg, assets folder, and this README.md) directly into the repository's top level. Do not upload the ZIP or enclosing folder. Commit directly to main.
3. Settings > Pages > Build and deployment: Source = Deploy from a branch, Branch = main, Folder = /(root). Click Save.
4. Wait for deployment. Your site will be https://YOURUSERNAME.github.io/cairn-shared-pool/ . Replace YOURUSERNAME with your GitHub username.
5. Visit https://YOURUSERNAME.github.io/cairn-shared-pool/manifest.json and confirm you see JSON text rather than a 404.
6. In your Owlbear profile, Add Extension using that full manifest URL. Enable it in your room's extension settings.
7. Each player opens the dice icon and adds dice. Once all dice are visible, the GM clicks Roll pool. New pool resets the round.

The repository name matters: these files use /cairn-shared-pool/ paths. Do not rename the repository or configure a custom domain without updating those paths.

The direct website shows an installation message until embedded inside an Owlbear room. Disabled controls there are expected. Players use the extension inside Owlbear; they do not need GitHub accounts.

## Checks and limits

Production build and automated core roll tests pass. Live multi-user Owlbear testing is still needed. Try a pool with a second person before game night.

Each player can add up to 12 dice, with 60 dice maximum in the pool. Use one room tab per person and preferably one GM. Wait for contributions to appear before rolling; late additions are not included in the roll snapshot. Leaving the room removes a player's unrolled contribution. A completed result remains until New pool. Use New pool to recover a stuck roll.

This displays raw highest damage only; apply armour separately. All tied highest dice are highlighted. GitHub serves the application files; shared pool data and results synchronize through Owlbear.

## Updating

Upload replacement ready-to-host files to the same repository and commit to main. Pages republishes automatically. Keep the repository name and manifest URL unchanged.

Original editable source is in the separate Cairn-Shared-Pool.zip package. To rebuild for this deployment: run `npm ci`, then `npx vite build --base=/cairn-shared-pool/`; update all manifest icon/popover paths to start with `/cairn-shared-pool/`, then upload the resulting dist contents.

## Official documentation

- https://docs.github.com/en/pages/getting-started-with-github-pages/creating-a-github-pages-site
- https://docs.github.com/en/pages/getting-started-with-github-pages/configuring-a-publishing-source-for-your-github-pages-site
- https://docs.github.com/en/repositories/working-with-files/managing-files/adding-a-file-to-a-repository
- https://extensions.owlbear.rodeo/
