# Epidemos

**Epidemiology in disasters, emergencies, and outbreak settings.**

Website for [Epidemos Ltd](https://epidemos.github.io) — a public-health consultancy specialising in field epidemiology, data science, and capacity building in humanitarian and emergency contexts.

---

## Tech stack

| Layer | Technology |
|---|---|
| Static site generator | [Jekyll](https://jekyllrb.com/) |
| Hosting | [GitHub Pages](https://pages.github.com/) |
| CSS | Custom (no framework) — CSS custom properties, Grid, Flexbox |
| Fonts | [Montserrat](https://fonts.google.com/specimen/Montserrat) + [Inter](https://fonts.google.com/specimen/Inter) via Google Fonts |
| Forms | [Formspree](https://formspree.io/) |

---

## Run locally

```bash
gem install jekyll
jekyll serve
# → http://localhost:4000
```

---

## Update content

### Team members / bio
Edit `_config.yml` under the `people:` key. Each entry takes:
```yaml
- name: Full Name
  pic: 1          # filename in /img/team/ (without extension)
  position: Title
  social:
    - title: linkedin
      url: https://...
  bio: "<p>HTML biography text...</p>"
```

### Services
Edit `_includes/services.html`.

### Approach section
Edit `_includes/approach.html`.

### Contact form
The form posts to Formspree. The recipient email is set in `_includes/contact.html` via an obfuscated JS string. Update `_config.yml` → `email` and the JS in that file if the address changes.

### Logo
The logo mark is `img/logo.svg` — an SVG geodesic globe with a teal "E" node pattern. Replace or edit directly.

---

## Structure

```
├── _config.yml          # Site settings, team data
├── _includes/
│   ├── head.html        # <head> — meta, fonts, stylesheet
│   ├── header.html      # Nav + hero + photo strip
│   ├── services.html    # Services section
│   ├── approach.html    # Approach / values section
│   ├── contact.html     # Contact form (Formspree)
│   └── footer.html      # Footer
├── _layouts/
│   ├── default.html     # Homepage layout
│   └── about.html       # About page layout
├── about/index.html     # About page (uses about layout)
├── img/
│   ├── logo.svg         # Logo mark (geodesic globe)
│   └── sl_map.jpg       # Hero photo strip
└── style.css            # All styles
```

---

## Deployment

Every push to `master` triggers an automatic GitHub Pages build and deploy. Allow ~1 minute for changes to appear at **https://epidemos.github.io**.
