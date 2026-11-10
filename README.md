# Reader Study – GitHub Pages (Option A)

## Included
- `index.html`: Reader Study viewer, local autosave, CSV import/export, and Admin dashboard.
- `cases_s1.js`: metadata for Session 1 (94 cases) and two-reader configuration.
- `img_s1/README.txt`: instructions for the missing CT sprite-sheet images.
- `.nojekyll`: disables Jekyll processing for this static site.

## Important limitation
This is a static GitHub Pages deployment. Each reader's answers are stored in that reader's browser (`localStorage`). There is **no automatic synchronization** between readers or devices. Each reader must export their session CSV and send it to the coordinator. The coordinator opens **Admin dashboard**, selects the session, uploads the two CSV files (reader_A and reader_B), and reviews the comparison.

The Admin dashboard runs locally in the browser. It does not upload the CSV files to GitHub or another server.

## Before deployment: add the image assets
The supplied `cases_s1.js` references files under `img_s1/` (for example `img_s1/S1-001.png`). The two uploaded source files did not include these PNG images. Copy the complete image set into `img_s1/` before testing/deployment. Check that every `src` path in `cases_s1.js` matches an actual filename exactly (including capitalization).

If you also use Session 2, add `cases_s2.js` and its corresponding image folder/assets. Session 2 is optional and remains disabled until `cases_s2.js` is present.

## Deploy free with GitHub Pages
1. Sign in to GitHub and create a **new public repository**, for example `reader-study`. GitHub Free requires a public repository for GitHub Pages.
2. Upload the contents of this folder to the **root** of the repository. The root should contain `index.html`, `cases_s1.js`, `.nojekyll`, and `img_s1/`.
3. Open the repository → **Settings** → **Pages**.
4. Under **Build and deployment**, choose **Deploy from a branch**.
5. Choose branch **main** and folder **/(root)**, then click **Save**.
6. Wait for the deployment to finish. In Settings → Pages, click **Visit site**. The URL will usually be `https://YOUR-USERNAME.github.io/reader-study/`.
7. Open the site in a browser and test with one case before sending the URL to readers.

Official instructions: https://docs.github.com/en/pages/getting-started-with-github-pages/creating-a-github-pages-site

## Suggested operating procedure for two readers
1. Send the same website URL to both readers.
2. Reader A always selects `reader_A`; Reader B always selects `reader_B`.
3. Each reader should use the same browser/device throughout their session, because autosaved progress is stored locally in that browser.
4. At the end of each session, each reader clicks **Xuất CSV session này** and sends the CSV file to the coordinator.
5. The coordinator opens **Admin dashboard**, chooses the relevant session, uploads the matching reader_A and reader_B CSV files, then clicks **Phân tích / cập nhật dashboard**.
6. Download the combined CSV to archive or analyze in Excel/R/Python.

## Privacy and security
- A GitHub Pages site is public. Do not upload identifiable patient data, DICOM headers, names, dates of birth, accession numbers, or any confidential clinical material.
- The `reader_A` / `reader_B` selector is a workflow label, not authentication. Anyone who knows the public URL can open the app and choose either reader label.
- This dashboard is for local aggregation of de-identified study ratings, not for secure clinical data storage.
