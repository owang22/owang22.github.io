# owang22.github.io

Live site: **https://owang22.github.io**

Personal site, built by GitHub Pages with Jekyll. No theme or plugins: the layout lives in `_layouts/` and `_includes/`, styles in `assets/css/main.css`.

## Where things live

| Change | File |
|---|---|
| Bio, interests | `index.md` |
| News on the home page | `_data/news.yml` |
| Publications (`selected: true` puts one on the home page) | `_data/publications.yml` |
| Project cards | `_data/projects.yml` (optional images go in `assets/img/projects/`) |
| Personal page text | `personal.md` |
| Personal page photos | `_data/photos.yml` + images in `assets/img/personal/` |
| Profile photo | `assets/img/profile.jpg` (shows up automatically once the file exists) |
| CV | `assets/files/cv.pdf` |
| Email, GitHub, Scholar, LinkedIn icons | `_config.yml` |

## Preview locally

```
gem install jekyll -v 3.10.0
jekyll serve
```

## Deploy

Push to `main`. Pages settings: deploy from branch `main`, folder `/ (root)`.
