# Shema Bible Translation - YWAM

This folder is a self-contained static site for the globe presentation.

## Files

- `index.html`: the full presentation app with embedded data, portraits, fonts, and logo
- `vercel.json`: minimal Vercel config
- `.gitignore`: local junk-file exclusions

## Local preview

From this folder:

```bash
python3 -m http.server 4173
```

Then open `http://localhost:4173`.

## Update the deployed site

The source generator lives here:

- `../obt-projects-globe/build_globe.py`

When you regenerate the app, copy the fresh output over this folder's `index.html`.

Example:

```bash
python3 ../obt-projects-globe/build_globe.py
cp ../obt-projects-globe/index.html ./index.html
```

## GitHub + Vercel deployment

### Recommended: dedicated GitHub repo

1. Create a new empty GitHub repository.
2. Copy the contents of this folder into that repository.
3. Commit and push.
4. In Vercel, choose `Add New... -> Project`.
5. Import the GitHub repository.
6. If Vercel asks for a framework preset, choose `Other`.
7. Leave Build Command empty.
8. Leave Output Directory empty.
9. Deploy.

### Alternative: deploy from the current repo as a subfolder

1. Push the whole workspace repository to GitHub.
2. In Vercel, import that repository.
3. Set the Root Directory to:

```text
shema-bible-translation-ywam-site
```

4. If prompted, use the `Other` framework preset.
5. Leave Build Command and Output Directory empty.
6. Deploy.

## Notes

- No environment variables are required.
- No database or serverless functions are required.
- The app is large because the media and data are embedded directly into `index.html`.
