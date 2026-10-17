# Publishing this e-portfolio — step-by-step

Run these commands from the folder that contains this file (`srm-eportfolio/`). Replace `<your-username>` with your GitHub username.

## 1. Initialise the local repository

```bash
cd srm-eportfolio
git init
git add -A
git commit -m "SRM_PCOM7E e-portfolio: complete submission"
```

## 2. Create the GitHub repository

1. Go to github.com → **New repository**.
2. Name it (e.g. `srm-eportfolio`) and set it to **Public** (GitHub Pages is free only for public repos; a private repo requires GitHub Pro).
3. Do **not** initialise it with a README or licence — this repo already has one.

## 3. Push to GitHub

```bash
git branch -M main
git remote add origin https://github.com/<your-username>/srm-eportfolio.git
git push -u origin main
```

If you use two-factor authentication, GitHub no longer accepts account passwords for pushes — use a Personal Access Token (Settings → Developer settings → Personal access tokens → Tokens (classic), scope `repo`) as the password, or set up the `gh` CLI / SSH keys.

## 4. Enable GitHub Pages

1. Repository → **Settings** → **Pages**.
2. Source: **Deploy from a branch**; Branch: `main`, folder: `/ (root)`.
3. Save. After a minute the site is live at `https://<your-username>.github.io/srm-eportfolio/`.
4. Check that `index.md` renders as the home page and that every link on it resolves (the per-unit stubs are placeholders until you add the remaining artefacts). The YAML front matter at the top of `index.md` is already Jekyll-compatible, so the Markdown renders automatically with no extra configuration.

## 5. Create the submission branch (do this last, once the site looks right)

The brief requires the submitted portfolio to be a branch that is **not changed after the deadline**:

```bash
git checkout -b submission
git push -u origin submission
```

From then on, make no further commits to `submission`. If you fix anything later, do it on `main` and create a fresh submission branch rather than touching the frozen one.

## 6. Submit

1. Export the reflective piece to MS Word or PDF, with the e-portfolio URL (`https://<your-username>.github.io/srm-eportfolio/`) in the header or title.
2. Upload that document to the submission portal. If the portal offers a Turnitin draft check, run it first.

## Notes

- The DOCX artefacts (`executive_summary.docx`, `executive_summary_v2.docx`, `Pampered_Pets_Risk_Identification_Report_2.docx`) and the PDF are uploaded as binary files — GitHub displays them as download links, which is fine for a portfolio.
- Keep the PDF's original filename (`12701559_-_Executive_Summary.pdf`) — it is the graded artefact and the filename is part of its provenance.
- Before pushing, fill the two `TODO` placeholders in `team-exercises/README.html` (your individual contribution statement and any supporting evidence).
