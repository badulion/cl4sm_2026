# Constrained Learning for Scientific Modelling — website

Single-page Jekyll site for the ELLIS session (December 8, 2026), built for GitHub Pages.

## Editing content

| What | Where |
|---|---|
| Event host/location, session start time, CMT link, template link, contact email | `_config.yml` |
| Important dates (fill in `date`; until then `approx` + "TBA" is shown) | `_data/dates.yml` |
| Schedule (minutes from session start; real clock times appear once `event.start_time` is set) | `_data/schedule.yml` |
| Topics | `_data/topics.yml` |
| Keynote speaker / organisers / Program Committee | `_data/speakers.yml`, `_data/organizers.yml`, `_data/pc.yml` |
| Page text (About, Call for Contributions) | `index.html` |
| Styles | `assets/css/style.css` |

Photos: drop images into `assets/img/` and set `photo: assets/img/<file>.jpg` for the person. Without a photo, their initials are shown.

## Local preview

```sh
bundle install
bundle exec jekyll serve
```

Or without a local Ruby install:

```sh
docker run --rm -it -p 4000:4000 -v "$PWD":/srv/jekyll -w /srv/jekyll ruby:3.3 \
  bash -c "bundle install && bundle exec jekyll serve --host 0.0.0.0"
```

## Deploying to GitHub Pages

Push to GitHub, then go to **Settings → Pages → Deploy from a branch** and pick your branch with `/ (root)`.
If the site is served from `https://<user>.github.io/<repo>/`, set `baseurl: "/<repo>"` in `_config.yml`.
