# Video Automation Publisher

A GitHub Pages front end for preparing video publishing details and initiating TikTok Login Kit authorization.

## GitHub Pages

The site is published from the repository's `main` branch.

- Home: https://kareemkhaled111.github.io/video-automation-publisher/
- OAuth redirect page: https://kareemkhaled111.github.io/video-automation-publisher/callback.html
- Terms: https://kareemkhaled111.github.io/video-automation-publisher/terms.html
- Privacy: https://kareemkhaled111.github.io/video-automation-publisher/privacy.html

## TikTok app configuration

Register this exact redirect URI in the TikTok Developer app:

`https://kareemkhaled111.github.io/video-automation-publisher/callback.html`

The page requests these scopes:

- `user.info.basic`
- `video.upload`
- `video.publish`

The user enters the Production Client Key in the page. The Client Secret must never be added to this repository or browser code.

## Security and deployment boundary

GitHub Pages is static hosting. This repository can host the user interface, launch the TikTok authorization redirect, and validate the OAuth `state` on return. It cannot securely exchange an authorization code for tokens, store refresh tokens, or upload/publish videos because those operations require a trusted server-side component holding the TikTok Client Secret.

The callback page intentionally does not pretend that authorization is complete and does not expose or store account tokens. A secure server-side OAuth/token and Content Posting API component is required for a real end-to-end connection and publishing flow.

## Local preview

Open `index.html` in a browser or serve the repository with any static HTTP server. OAuth redirect testing requires the deployed HTTPS GitHub Pages URL to be registered in TikTok Developer settings.
