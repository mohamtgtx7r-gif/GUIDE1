# Netlify deployment instructions

This is the original Lovable/TanStack Start SSR source project with an added `netlify.toml`.
It is **not** a prebuilt static website. Do not upload this source ZIP to Netlify's manual drag-and-drop area.

1. Extract this ZIP.
2. Upload the project files to a GitHub repository connected to your Netlify account. Keep `netlify.toml` at the repository root.
3. In Netlify choose **Add new project > Import an existing project > GitHub** and select the repository.
4. Build command: `npm run build`.
5. Publish directory: `.output/public`.
6. Environment variable: `NITRO_PRESET=netlify` (also specified in `netlify.toml`).
7. Deploy, then check the deployment logs and test every page.

This project uses `@lovable.dev/vite-tanstack-config`, which may apply its own Nitro defaults. The Netlify preset and output path have **not been build-tested** in this environment because npm package downloads are unavailable. If the build fails, inspect the first relevant error in the Netlify deploy log; the preset may need to be overridden in the Lovable Vite config.

Note: The existing contact form may not be wired to an email backend. Deployment does not automatically make it functional.
