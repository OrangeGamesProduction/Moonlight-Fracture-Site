# News preview pages

These static pages provide article metadata to social apps that do not run the site's JavaScript. After news changes in the `wikiNews` Firestore collection, run `npm run build` in the Moonlight-Fracture-Site-Development repository, then copy its generated `dist/moonlight-fracture-site/browser/news/` output into this repository's root `news/` folder before publishing. Keep the generated article folders in sync with the currently published documents.
