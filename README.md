# RSH Regulatory Intelligence Portal

An interactive web portal for exploring Regulator of Social Housing (RSH) regulatory judgements across 290 registered providers in England.

## What it does

- **Search & filter** all 290 providers by name, registration code, provider type, or consumer grade
- **Provider profiles** — RSH consumer, governance and viability grades with full findings and improvement actions
- **Sector benchmarking** — see how a provider's grades compare to the distribution across their peer group
- **Similar providers** — browse providers of the same type and grade tier

## Planned features

- [ ] Geographic clustering — see providers within a set distance
- [ ] Direct links to live RSH judgements on GOV.UK
- [ ] Grade change timeline / history view

## Data source

Regulator of Social Housing — GOV.UK  
Published: April 2026  
290 registered providers (205 Private Registered Providers, 85 Local Authorities)

## How to run locally

Just open `index.html` in a browser — no server or build step needed. Everything is self-contained in a single HTML file.

## How to update the data

The provider data is embedded as a JavaScript array (`const DATA = [...]`) near the top of `index.html`. To update:

1. Export a new version of the RSH judgements spreadsheet
2. Replace the `DATA` array with the updated records
3. Commit and push — GitHub Pages will update automatically within a minute or two

## Project structure

```
rsh-portal/
├── index.html        # The entire portal — self-contained HTML/CSS/JS
└── README.md         # This file
```

## Built with

- Vanilla HTML, CSS and JavaScript (no frameworks, no build tools)
- DM Sans + DM Serif Display (Google Fonts)
- Data: RSH regulatory judgements, April 2026
