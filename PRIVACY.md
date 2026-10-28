# Privacy policy for Rat Jar

Effective date: 2026-10-27

Rat Jar is a Chrome extension that saves the cookies of your logins in an encrypted vault on your computer and swaps them so you can switch between accounts. This policy explains what the extension handles, where it is kept, and what never happens to it.

## What the extension handles

- Cookies of the websites you stash. These are session and login cookies, which the Chrome Web Store classifies as authentication information. They are read when you stash a site and written back when you switch.
- The names of your stashes and the domains of the sites in them.
- In "one stash per tab" mode, the addresses of your open tabs on stashed sites, so each tab finds its stash again after a restart.
- The mode flag and the order of your stashes.

Nothing else. The extension does not read page content, form fields, browsing history, or anything you type.

## Where it is kept

- All of it stays in Chrome's extension storage on your own device.
- Cookies, stash names and site names are stored as one AES-256-GCM encrypted record. The encryption key is derived from your passphrase with PBKDF2-SHA256 (600,000 iterations, random salt). The passphrase itself is never stored.
- While the extension is unlocked, the derived key is kept in extension storage so the browser can restart without asking for the passphrase. Lock it (the moon button) and the key is removed; the record is then unreadable without the passphrase.
- The tab addresses used by "one stash per tab" mode are stored unencrypted, as a plain list of addresses and stash ids, so tabs can be matched before the vault is read.
- A backup file you export is the encrypted record exactly as stored. It is useless without the passphrase in use when it was exported.

## What never happens

- No data is sent anywhere. The extension makes no network requests and has no server, no account, no sync, no analytics, no crash reporting and no advertising.
- No data is sold, shared or transferred to any third party.
- No content scripts are injected into web pages. No remote code is loaded.
- No data is used for any purpose other than switching your accounts.

## Permissions

- cookies: read and write the cookies of the sites you stash.
- storage: keep the encrypted vault and the per-tab pins on this device.
- activeTab: see the address of the tab in front when you open the popup.
- declarativeNetRequestWithHostAccess: in "one stash per tab" mode, block a background tab whose stash is not live from reaching stashed sites, so it never sends a request as the wrong account. The rules hold tab ids and site domains only and read or rewrite nothing.
- Host access is requested per site, at the moment you stash it, never for all sites at install.

## Deleting your data

Click "Burn the burrow" on the locked screen to delete every stash, or remove the extension from Chrome. Both erase everything the extension stored. A backup file you saved yourself stays wherever you put it.

## Changes

Changes to this policy are published in this file, with the effective date updated. The current version is always at https://github.com/antonylgs/rat-jar-privacy-policy/blob/main/PRIVACY.md.

## Contact

Open an issue at https://github.com/antonylgs/rat-jar-privacy-policy/issues.
