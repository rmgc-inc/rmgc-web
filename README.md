# RMGC Construction Inc.

Portable static website. Requires Node.js 20 or newer for the included tools.
No runtime dependencies, Replit account, database, or server secrets are required.

## Upload to GitHub

Extract the archive and upload the **contents** of `rmgc-website` into the
repository root. `package.json`, `index.html`, `assets`, `admin`, and `content`
should be visible at the top level, not nested inside an extra folder.

## Run locally

```sh
npm ci
npm test
npm start
```

Open http://localhost:3000. Set `PORT` to choose another port.

## Deploy

Connect your GitHub repository to Netlify or Vercel; configuration is included.
For other static hosts use:

- Build command: `npm run build`
- Output/publish directory: `dist`
- Node.js: 20 or newer
- Framework: Other / static

For a Node hosting service, use `npm start` (it respects `PORT`).
For a plain web server, upload the contents of `dist`.
Host at the domain root. GitHub Pages project subpaths such as
`username.github.io/repository/` are not supported without URL changes;
use a custom domain or root-level user/organization Pages site.

## Included content and enquiries

All currently synced project photos, captions and site content are included.
Images in the content file use local deployment paths, not the old repository.
The estimate form submits to `https://formspree.io/f/mrpgnjol`.
The contact email is info@rmgcinc.ca. Formspree controls email delivery;
automatic customer replies are not enabled by this export.

## Important: connect the editor to YOUR repository

The public website works without CMS login. The editor at `/admin/` requires
separate GitHub OAuth configuration:

1. In `admin/config.yml`, replace `YOUR_GITHUB_USERNAME/YOUR_REPOSITORY` with
   your repository and confirm its branch is `main`.
2. Set `base_url` to a Decap-compatible OAuth proxy you control. Configure its
   GitHub OAuth application and callback URL using your proxy provider's
   instructions. Store OAuth secrets only in the proxy provider's secret store,
   never in this repository.
3. Give the owner write access to the new repository.
4. Keep `media_folder: assets/uploads` and `public_folder: /assets/uploads`.
5. Configure your hosting service to redeploy automatically when `main` changes.

CMS edits then commit to this repository and trigger a new deployment.
New image uploads are included in that deployment; large uploads should be
optimized for web performance. Edits saved to the OLD repository will not
update the new website. Keep using the old editor until the new one is configured.

## Release checks

Run `npm test && npm run build`, then `npm run preview` to check the built site.
Review galleries, mobile navigation and the estimate form after deployment.
No real form enquiry was sent during export verification.
