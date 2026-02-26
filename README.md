# Indivisible Carson City

Website for Indivisible Carson City — a local grassroots group promoting progressive values and civic engagement in Carson City, Nevada.

## Tech Stack

- [Jekyll 4](https://jekyllrb.com/) — static site generator
- [Bootstrap 5](https://getbootstrap.com/) — CSS framework (via CDN)
- [Decap CMS](https://decapcms.org/) — content management for non-technical editors
- [Netlify](https://www.netlify.com/) — hosting, identity, and Git Gateway

## Local Development

### Prerequisites

- [rbenv](https://github.com/rbenv/rbenv) with Ruby 3.3.6
- Bundler (`gem install bundler`)

### Setup

```bash
git clone <your-repo-url>
cd indivisible_site
rbenv install 3.3.6    # if not already installed
bundle install
```

### Run Locally

```bash
bundle exec jekyll serve --future
```

Open [http://localhost:4000](http://localhost:4000)

## Content Editing

Non-technical editors can manage content through the CMS at `/admin`. You'll need a Netlify Identity invitation to log in.

### What's Editable via CMS

- **Blog posts** — create, edit, and publish from the browser
- **Events** — update the upcoming events list
- **About page** — edit the about page content
- **Navigation** — add or reorder nav links

### Adding Content Directly

- **Blog posts:** Add a Markdown file to `_posts/` named `YYYY-MM-DD-title.md`
- **Events:** Edit `_data/events.yml`
- **Pages:** Edit `about.md` or add new Markdown files in the root

## Deploying

1. Create a GitHub repo and push this code
2. Connect the repo to [Netlify](https://app.netlify.com/)
3. In the Netlify dashboard:
   - Enable **Netlify Identity** (Settings > Identity)
   - Enable **Git Gateway** (Settings > Identity > Services)
   - Set registration to **Invite only**
4. Invite your first CMS user via the Identity tab
5. Update `url` in `_config.yml` to your Netlify URL

Netlify will auto-build on every push to `main`. The build settings are in `netlify.toml`.

## Project Structure

```
├── _config.yml          # Jekyll configuration
├── _layouts/            # Page templates (default, home, post, page)
├── _includes/           # Reusable components (nav, footer, cards)
├── _posts/              # Blog posts (Markdown)
├── _data/
│   ├── events.yml       # Upcoming events
│   └── navigation.yml   # Nav links
├── admin/               # Decap CMS
├── assets/
│   ├── css/custom.css   # Brand overrides
│   └── uploads/         # CMS media uploads
├── index.md             # Homepage
├── blog.html            # Blog listing
├── about.md             # About page
└── 404.html             # Custom 404
```
