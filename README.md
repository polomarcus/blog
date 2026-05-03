# Blog
To centralize my blog posts from dev.to / medium

## Start the blog locally
First time only — initialize the theme submodule (otherwise every page returns 404):
```
git submodule update --init --recursive
```

Then:
```
docker-compose up
# check http://localhost:1313/blog/
```

Or

```
hugo serve --buildDrafts --buildFuture
```
## How to write an article
Create a markdown file inside `content/article`.

The cover image is rendered from the `thumbnail:` frontmatter field (not `images:`, which only feeds OpenGraph/Twitter metadata). Both should point at the same file:

```yaml
thumbnail: "images/2026/my_article.png"
images:
    - "images/2026/my_article.png"
```

## How to generate a cover image

I use [badele/slide-generator](https://github.com/badele/slide-generator) for cover images.

### One-time setup
```
brew install imagemagick
git clone https://github.com/badele/slide-generator ~/projects/slide-generator
```

### Generate a slide
The `user_post` profile expects `TEXT10..TEXT14` (the README in the upstream repo says `TEXT2..TEXT6`, but `test_config.yaml` is authoritative). The default `NEXTART-Heavy` font isn't bundled, so override with system Arial Black.

Template — adapt the text values for your article:

```bash
cd ~/projects/slide-generator && ./generate_slide.sh --profile user_post \
  --set TEXT_FONT_STYLE="/System/Library/Fonts/Supplemental/Arial Black.ttf" \
  --set TEXT11_FONT_STYLE="/System/Library/Fonts/Supplemental/Arial.ttf" \
  --set TEXT12="DevPO" \
  --set TEXT12_FONT_SIZE=140 \
  --set TEXT12_GEOMETRY="+58+120" \
  --set TEXT13="L'ingénieur reprend le produit" \
  --set TEXT13_FONT_SIZE=46 \
  --set TEXT13_GEOMETRY="+58+320" \
  --set TEXT14="Et l'AI lui en donne enfin le temps" \
  --set TEXT14_FONT_SIZE=46 \
  --set TEXT14_GEOMETRY="+58+395" \
  --set TEXT11="Paul Leclercq · epauler.fr · 2026" \
  --set TEXT11_FONT_SIZE=32 \
  --set TEXT11_GEOMETRY="+58+615"
```

Slot guide for this layout:
- `TEXT12` — big yellow title (top)
- `TEXT13` / `TEXT14` — two subtitle lines (middle)
- `TEXT11` — byline (bottom)

### Move it into the blog
```
cp ~/projects/slide-generator/output.png static/images/<year>/<slug>.png
```

Then add `thumbnail:` + `images:` entries to the article frontmatter (see "How to write an article" above).

## Blog engine
https://gohugo.io/getting-started/

## Blog theme
https://github.com/lxndrblz/anatole

### Shorcuts
https://gohugo.io/content-management/shortcodes/#figure

## Deploy
https://gohugo.io/hosting-and-deployment/hosting-on-github/

### Thanks
* https://github.com/badele
* open source contributors
["Standing on the shoulders of giants"](https://en.wikipedia.org/wiki/Standing_on_the_shoulders_of_giants)
