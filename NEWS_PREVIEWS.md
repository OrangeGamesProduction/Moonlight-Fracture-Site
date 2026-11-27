# News preview pages

These static pages provide article metadata to social apps that do not run the site's JavaScript. The Development site's Firebase trigger sends a `wiki-news-changed` repository dispatch for each created, updated, or deleted document in the `wikiNews` Firestore collection. This repository generates or removes only that article's preview and publishes the change to `master`; GitHub Pages then deploys it automatically.

An article preview URL becomes available after the workflow and the subsequent GitHub Pages deployment complete. The workflow run in Actions can be used to check publishing progress. Keep the generated article folders in sync with the currently published documents.

## Required publishing secret

The workflow uses a fine-grained personal access token to push preview commits because pushes made with the workflow's `GITHUB_TOKEN` do not start a GitHub Pages deployment. Create a fine-grained token limited to this repository with **Contents: read and write** permission, then add it under **Settings > Secrets and variables > Actions** with the name `PAGES_REPO_TOKEN`. The workflow fails with a setup error if this secret is missing. Its `GITHUB_TOKEN` is limited to read-only contents access for checkout.
