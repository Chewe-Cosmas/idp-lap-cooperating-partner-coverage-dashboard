# Integrated Development Plans (IDPs) & Local Area Plans (LAPs) Cooperating Partner Coverage Dashboard

Published by the Ministry of Local Government and Rural Development, Department of Physical Planning.

## Application type

This is a self-contained static web application. It has no build step, backend, database, package installation, or environment variables. All HTML, CSS, JavaScript, map data, and imagery required at runtime are stored in this folder and referenced with relative paths.

## Production files

- index.html — application entry point
- styles.css — responsive dashboard styling
- app.js — filters, map interaction, popups, register, sharing and export behavior
- data.js — browser-ready spatial and commitment data
- logo-medium.webp — Coat of Arms used in the official header
- inspection-report.md — source-data inspection and quality notes
- _headers — optional security and caching headers for compatible hosts
- .nojekyll — prevents GitHub Pages from applying Jekyll processing
- .github/workflows/pages.yml — GitHub Pages deployment workflow

## Test the production version locally

From the project workspace, run:

~~~powershell
python -m http.server 8080 --directory outputs
~~~

Then open http://localhost:8080/ in a browser. Do not use a file URL for final acceptance because public hosting serves the application over HTTP or HTTPS.

No compilation or export command is needed: outputs is already the production build.

## Deploy with GitHub Pages

1. Create an empty GitHub repository.
2. Upload or commit the contents of the outputs folder to the repository root. The repository root must contain index.html.
3. Open Settings > Pages in the repository.
4. Under Build and deployment, select GitHub Actions.
5. Push to the main branch. The included workflow publishes the site.
6. Open the deployment URL shown in the workflow summary. It normally follows this pattern: https://YOUR-GITHUB-USERNAME.github.io/YOUR-REPOSITORY-NAME/
7. Test the public URL, filters, map identify popups, share links, and CSV export.

### Command-line GitHub upload

Run these commands from inside the outputs folder after creating the empty repository:

~~~powershell
git init
git add .
git commit -m "Deploy IDP and LAP coverage dashboard"
git branch -M main
git remote add origin https://github.com/YOUR-GITHUB-USERNAME/YOUR-REPOSITORY-NAME.git
git push -u origin main
~~~

## Alternative: Netlify

Drag the entire outputs folder into Netlify Drop, or connect a repository and set its publish directory to outputs. No build command is required. Netlify will apply the included _headers rules.

## Alternative: Vercel

Create a Vercel project, select Other as the framework preset, leave the build command empty, and set the output directory to outputs.

## Environment and hosting settings

- Environment variables: none
- Build command: none
- Publish folder: outputs, or its contents when placed at the repository root
- Entry file: index.html
- Required protocol online: HTTPS, supplied automatically by the recommended hosts

## Release checklist

- [x] HTML, CSS, JavaScript, spatial data, and logo included locally
- [x] Runtime asset references are relative
- [x] No local-machine or file paths in the deployable package
- [x] No external fonts, icons, tile services, or API keys required
- [x] No environment variables required
- [x] Static-host deployment workflow included
- [x] Production version tested over HTTP
- [x] Desktop and mobile layouts verified
- [ ] Publish the folder and test the final public HTTPS URL
