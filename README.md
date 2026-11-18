# NRL ARC Estimation Portal — GitHub Pages package

## Deployment model
- Public static website; no login, password, authentication, backend, or database.
- Users upload their own Excel workbook in the browser and download the resulting estimate.
- Workbook parsing and estimation are performed client-side. The uploaded workbook is not sent to GitHub Pages by this application.
- No shared user accounts, central estimation history, server-side workbook storage, or approval workflow.

## Files
- `index.html` — complete application. Keep this file at the repository root.
- `.nojekyll` — tells GitHub Pages not to run Jekyll processing on the static site.

## Publish on GitHub Pages (no command line required)
1. Sign in to GitHub.
2. Select **New repository**. Suggested repository name: `NRL-ARC-Estimation`.
3. Set repository visibility to **Public** (required for GitHub Free Pages). Do not initialize with files if you plan to upload this package immediately; initializing with README is also fine.
4. Open the new repository and select **Add file → Upload files**.
5. Extract this ZIP on your computer. Upload `index.html`, `.nojekyll`, and this `README.md` from the extracted folder. Do not upload the ZIP itself as the only file.
6. Commit the files to the `main` branch.
7. Open **Settings → Pages**.
8. Under **Build and deployment**, set **Source** to **Deploy from a branch**.
9. Set **Branch** to `main` and folder to `/(root)`, then click **Save**.
10. Wait for the Pages deployment to complete. Open the URL shown in **Settings → Pages**. For a project repository it will normally be `https://<github-username>.github.io/NRL-ARC-Estimation/`.

## After deployment
- Open the website and test **Input template**, **Load example data**, Excel upload, Six-Tenths comparable selection/manual entry, calculation, and Excel export.
- Test with a non-confidential workbook first. Confirm the exported workbook opens correctly in Excel.
- The website is public to anyone who knows or discovers its URL. GitHub Pages sites are publicly accessible even when repository privacy options differ by plan.

## Security and governance warning
The application source contains its embedded EED WPI/CPI rate data and a blank input-template workbook. Both the repository source and published website are publicly accessible. Obtain NRL approval for public release of the application, embedded rate schedule, labels, and any organizational material before publishing. Never commit actual LPP workbooks, procurement estimates, vendor quotations, or confidential data to this repository. Uploading an Excel workbook through the application is designed to remain in the user's browser; this does not make the public website or its source private.

## Technical notes
- Static HTML; no build command, backend, database, environment variables, or secrets required.
- Each visitor runs an independent browser session. Data is not shared between visitors.
- JavaScript syntax was checked before packaging. A full live GitHub Pages deployment and browser end-to-end test have not yet been performed.
