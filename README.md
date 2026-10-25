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

Files go into one release called `files`. Each one gets a link like
`github.com/you/repo/releases/download/files/name.zip` that downloads directly. The list on the page is read
from that release, so it shows on any device where you've entered the token. Delete removes the file from the release.

## GitHub's limits

- 2 GB per file (GitHub's cap for release files), any file type including zip and exe
- About 1000 files in this release
- The repo must be public for other people to download
- Folders can't be uploaded, zip them first
