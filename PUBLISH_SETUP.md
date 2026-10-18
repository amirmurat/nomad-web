# One-time GitHub Pages setup

## 1. Create a fine-grained token

In GitHub: Settings → Developer settings → Personal access tokens → Fine-grained tokens → Generate new token.

- Resource owner: `amirmurat`.
- Repository access: **Only select repositories → `nomad-web`**.
- Repository permissions: **Contents → Read and write**. No other write permissions.
- Use a reasonable expiration and renew it when required.

Copy the token; GitHub displays it only once.

## 2. Store the token ONLY in the private source repository

Open: https://github.com/amirmurat/nomad/settings/secrets/actions

New repository secret:
- Name: `NOMAD_WEB_PUBLISH_TOKEN`
- Value: the token you created.

**Never paste this token into chat, issues, public files, or source code.**

## 3. Enable GitHub Pages

Open: https://github.com/amirmurat/nomad-web/settings/pages

- Build and deployment → Source: **GitHub Actions**.

## 4. Deploy

Push a commit to the private branch `feat/web-playtest` or manually run the private workflow `Nomad Web build`. After the successful build, the workflow pushes compiled assets to the public `site` branch. The public workflow then publishes them to GitHub Pages.

Expected address: https://amirmurat.github.io/nomad-web/

If publishing fails, inspect the private `Nomad Web build` workflow and the public `Publish Nomad Web` workflow. The `site` branch must contain only generated browser files.

GitHub Pages serves public assets. It does not protect game assets against downloading.
