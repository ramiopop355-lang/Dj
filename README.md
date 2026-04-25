# SIGMA Σ — Android AAB Build Pipeline

  This repository **only** holds the Android build pipeline for the SIGMA PWA hosted at https://sigmaaidzbac.replit.app.

  ## How it works
  On any push to `twa-source/**` or via manual dispatch, GitHub Actions runs Bubblewrap, signs the AAB with the keystore restored from the `SIGMA_KEYSTORE_BASE64` secret, and uploads the result as a workflow artifact.

  See `twa-source/README.md` for full setup instructions (3 GitHub Secrets to add, then run the workflow).

  ## Trigger a build manually
  Actions tab → **Build Sigma Android AAB** → Run workflow → main → Run.

  ## Output
  Each successful run uploads an artifact `sigma-android-release` containing:
  - `app-release-bundle.aab` — upload to Google Play Console
  - `app-release-signed.apk` — sideload for direct testing
  