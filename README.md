# CardioTech

A responsive, static conference website for CardioTech’s Faro satellite event (14–16 December 2026) and Madrid conference (10–12 June 2027). Ready for GitHub Pages; no build step or runtime dependencies.

## Develop

```sh
python3 -m http.server 4173
```

Open http://localhost:4173. Edit `index.html` (content), `speaker-bios.html` (keynote biographies), `styles.css` (base layouts), `poster-theme.css` (poster styling, portraits and partner logos), or `app.js` (programme tabs, navigation and theme preference). Jost fonts are served locally from `assets/fonts/`. The original root-level heart logo and banner are used directly.

## Verify

```sh
node --check app.js
git diff --check
```

Check desktop and mobile layouts, keyboard navigation through all three programme tabs, the mobile menu, dark mode, expandable speaker lists, and external document/registration links. The map requires internet access. There is no build or automated test runner in the repository.

## Publish

The [deployment workflow](.github/workflows/deploy-pages.yml) publishes the site to **https://cardiotech2027.github.io/** after every push to `main`, including merged pull requests. It can also be run manually from **Actions → Deploy website to GitHub Pages → Run workflow** on `main`.

One-time setup: in this repository’s **Settings → Pages → Build and deployment**, set **Source** to **GitHub Actions**. Commit and push the workflow together with `index.html`, both stylesheets, `app.js`, the root logo and banner, and `assets/`. A local save or commit alone does not trigger deployment; the commit must be pushed to GitHub.

The workflow checks JavaScript syntax and publishes only the website files and assets, including the keynote biography subpage. Source presentations, reference PDFs, and contributor instructions are not included in the deployed artifact. No build step, package installation, personal access token, or custom domain is required. Check the **Actions** tab for deployment status; publication is complete when the workflow succeeds.

## Content sources

Content was checked on 12 October 2026 against the supplied CaixaResearch pages:

- [Introduction](https://caixaresearch.org/es/breakthrough-conferences-cardiotech-introduction)
- [Scientific committee](https://caixaresearch.org/es/breakthrough-conferences-cardiotech-scientific-committee)
- [Portugal programme](https://caixaresearch.org/es/breakthrough-conferences-cardiotech-programme-portugal) ([accessible English version](https://caixaresearch.org/en/breakthrough-conferences-cardiotech-programme-portugal))
- [Abstract submission](https://caixaresearch.org/es/breakthrough-conferences-cardiotech-abstract-submission)
- [Registration](https://caixaresearch.org/es/breakthrough-conferences-cardiotech-registration)
- [Portugal location and map](https://caixaresearch.org/es/breakthrough-conferences-cardiotech-practical-information-portugal)

Programme tabs present selected highlights, with the complete preliminary PDF linked. The introduction contains an inconsistent date in one paragraph; the site uses 14–16 December 2026, consistent with the programme, deadlines, venue and registration. Abstract submission is marked as coming soon. The live Faro registration form takes precedence over the registration page’s older “available soon” text. Madrid fees remain unannounced. Update these states as organisers publish details.

Keynote speaker cards link to individual profiles on [the keynote biographies page](speaker-bios.html). Profile text is based on the bios supplied in `assets/bios/`.

No visitor data is collected by this application. Theme preference is stored locally. Registration and abstract submission remain with their official providers; the venue uses a Google Maps embed.

## Poster theme and institution logos

The visual theme follows the white poster in `Promo_Poster.pptx`: cardiac imaging, an angled white title panel, black sans-serif typography, italic conference-series branding, and burgundy accents. Section names are semantic headings at 38–56 px, with larger navigation labels.

`assets/poster/` contains the unchanged extracted artwork. Institution logos appear in the closing partner section, without repeated text captions; the la Caixa Foundation logo also appears above the “Breakthrough Conferences” series mark in the opening. Six partner images are used from `assets/logos/`; [logo provenance](assets/logos/sources.json) records their sources. Logos retain their proportions and original colours; white versions sit on dark backgrounds. The collaboration group uses the supplied `CNIC.jpg` across three slots, followed by `UVa_rojo.png` and `ClinicBarcelona.jpg` in one slot each.

`assets/people/` contains verified portraits for speakers, committee members and administrative support. [Portrait provenance](assets/people/sources.json) records the public profile and image URL for each person. Photos are served locally and cropped with CSS. [Outstanding portraits](assets/people/README.md) lists people whose cards temporarily use initials. Keep affiliation text with people; do not add institution logos back to these cards.

The supplied poster and earlier root artwork remain unchanged. Conference dates continue to follow the verified official programme, rather than older draft dates embedded in the poster.
