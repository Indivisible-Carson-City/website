# Indivisible Carson City — Jekyll Site

## Quick Commands
```bash
eval "$(rbenv init - zsh)" && bundle exec jekyll serve --future   # Local dev server at localhost:4000
eval "$(rbenv init - zsh)" && bundle exec jekyll build             # Build to _site/
```

## Stack
- **Jekyll 4.4** (not github-pages gem)
- **Bootstrap 5.3 via CDN** — no build tools, no node_modules
- **Decap CMS v3** at `/admin` with Netlify Identity + Git Gateway
- **Ruby 3.3.6** via rbenv

## Branding
- Indivisible Blue: `#002147` (navbar, footer, primary buttons)
- Indivisible Red: `#BB133E` (accent buttons, CTAs)
- Headings: Roboto Condensed (Google Fonts)
- Body: system font stack

## Key Files
- `_data/events.yml` — event list (placeholder data, will eventually come from external API)
- `_data/navigation.yml` — nav links (editable via CMS)
- `admin/config.yml` — Decap CMS collections config
- `assets/css/custom.css` — brand overrides on top of Bootstrap
- `netlify.toml` — build config and security headers

## Conventions
- `future: true` is set in `_config.yml` so today's posts render locally
- Netlify Identity widget script is on every page (required for email confirmation flow)
- Default layout includes login redirect script for CMS users
- CMS media uploads go to `assets/uploads/`

## Do Not
- Commit `.claude/` or `_site/`
- Edit `Gemfile.lock` directly — run `bundle install` instead
- Add node_modules or JS build tools — Bootstrap is CDN-only
