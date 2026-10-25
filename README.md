# Ability Share (GitHub version)

A static site that runs on GitHub Pages. Upload a file, it is stored as a release file in your own repo,
and you get a direct download link. No server needed.

## Set up

1. Put these files at the top level of a **public** repo: `index.html`, `logo.svg`, `apple-touch-icon.png`,
   `manifest.webmanifest`, `.nojekyll`.
2. Repo **Settings**, **Pages**, deploy from the `main` branch, root folder.
3. Create a fine-grained token: GitHub **Settings**, **Developer settings**, **Personal access tokens**,
   **Fine-grained tokens**. Pick only this repo, and set **Contents** to **Read and write**.
4. Open your Pages site, tap the gear, enter `yourname/repo-name` and the token, then **Save and connect**.

The token is saved only in that browser. Never put it in the repo.

## How it works

Browsers can't upload to GitHub's release storage directly, so the page saves files in an `uploads` folder in your repo.
Links look like `raw.githubusercontent.com/you/repo/main/uploads/name.zip`. The list on the page is read from the repo,
so it shows on any device where you've entered the token. Delete removes the file from the repo.

For files bigger than about 70 MB: on GitHub open your repo, go to **Releases**, create or edit a release with the tag `files`,
and drag the file in (up to 2 GB). Those files show up in the page's list too, with direct download links.

## GitHub's limits

- About 70 MB per file when uploading through the page, 2 GB per file when added through the Releases page
- Any file type, including zip and exe
- The repo must be public for other people to download
- Folders can't be uploaded, zip them first
