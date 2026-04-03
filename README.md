# mamisoa-hugo

Custom Hugo theme for **Centre Médical Bruxelles-Schuman** — an ophthalmology practice in Brussels.

Forked from [Airspace Hugo](https://github.com/themefisher/airspace-hugo) and heavily customized.

## Features

- Trilingual support (FR/EN/NL)
- Go templates: layouts, partials, baseof, single, index
- Bootstrap-based responsive design with AOS animations
- Font Awesome icons
- JSON-LD structured data (MedicalBusiness, FAQPage)
- LLM discoverability output formats (llms.txt, llms-full.txt)
- Cal.com appointment booking integration
- Google Analytics 4 support

## Usage

This theme is loaded as a **git submodule** in the main site repository.

```bash
# Clone the site with the theme
git clone --recurse-submodules https://github.com/mamisoa/beta.ophtalmologiste.be.git

# Update the theme
cd themes/mamisoa-hugo
git pull origin master
cd ../..
git add themes/mamisoa-hugo
git commit -m "chore: update mamisoa-hugo submodule"
```

## Theme Assets

The theme provides shared assets in `static/`:

- `css/` — Base stylesheets (Bootstrap, theme CSS)
- `js/` — JavaScript (Bootstrap, AOS, custom scripts)
- `plugins/` — Third-party plugins
- `svg/` — SVG assets
- `videos/` — Background videos

**Note**: Site-specific assets (images, `css/style.css`, `i18n/*.toml`) live in the site root, not in the theme. This allows the theme to be updated independently.

## Deployment

The site is hosted on a Proxmox LXC (Ubuntu 24.04) behind Traefik reverse proxy with Caddy as web server.

```bash
# Deploy production (ophtalmologiste.be)
./deploy_ophtalmologiste.be.sh prod

# Deploy beta (beta.ophtalmologiste.be)
./deploy_ophtalmologiste.be.sh beta
```

Builds use Hugo environments (`--environment production` / `--environment development`) to set `baseURL` and `env` without modifying config files.

## License

Copyright (c) 2022 - Mamisoa Andriantafika
