# BusinessConsent CMP — Google Tag Manager template

Install the [BusinessConsent](https://businessconsent.com) consent banner through
Google Tag Manager, with Google Consent Mode v2 built in.

## What the tag does

1. Sets Google Consent Mode v2 defaults to **denied** — `ad_storage`,
   `analytics_storage`, `ad_user_data` and `ad_personalization` — before any
   other tag fires.
2. For a returning visitor, applies their stored choice straight away, so tags
   on the first page view already see the right consent.
3. Loads the BusinessConsent banner for your property.

After each decision the banner updates Consent Mode and pushes a
`bc_consent_update` event to the dataLayer, with `bc_consent.preferences`,
`bc_consent.statistics` and `bc_consent.marketing` set to `true` or `false`, for
tags that don't support Consent Mode.

## Setup

1. Add **BusinessConsent CMP** from the Community Template Gallery.
2. Create a tag from it and enter your **Property ID** (BusinessConsent
   dashboard → Properties → your website → Install).
3. Trigger: **Consent Initialization – All Pages**.
4. In *Admin → Container settings*, tick *Enable consent overview* and give your
   other tags the consent checks they need (for example `analytics_storage` for
   GA4).

Full guide: https://businessconsent.com/docs#google-tag-manager

Scripts hard-coded in your page HTML load before Tag Manager, so they can't be
held by the banner's automatic blocking. For those sites, paste the
BusinessConsent script tag at the top of `<head>` instead.

## Support

Report problems in this repository's
[Issues](https://github.com/Lazanjur/businessconsent-gtm-template/issues).
