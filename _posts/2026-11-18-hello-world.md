---
title: hello world
---

ey! this is the first post on my tiny blog. it's mostly a note to future me on how to write new posts, because I *will* forget.

## how I make a new post

1. I make a new file in `_posts/` named `YYYY-MM-DD-some-title.md`, for example `2026-12-01-my-cool-post.md`. the date and the title in the filename are required, Jekyll ignores the file otherwise. the part after the date becomes the URL, so I keep it lowercase with dashes.

2. at the very top of the file I put the front matter:

   ```markdown
   ---
   title: my cool post
   ---
   ```

   that's all I need, the layout is already set in `_config.yml`.

3. I write the post in markdown under that. **bold**, *italics*, `code`, [links](https://maru.olcese.com.ar), lists, headings with `##`, all of it works.

4. the **first paragraph** is what shows up as the preview on the homepage, so I try to make it a nice short intro. if I want a different preview, I add `excerpt: "whatever I want"` to the front matter.

5. I commit and push to `main`. GitHub Pages rebuilds the site by itself in a minute or two. the newest post goes on the homepage automatically and gets added to [all posts](/blog/).

## things I should remember

- **posts dated in the future don't show up.** if a post isn't appearing, I check the date in the filename first.
- if the site doesn't update at all, I look at the **Actions** tab on GitHub. the "pages build and deployment" run shows the error if Jekyll choked on something.
- for images, I put them in an `assets/` folder and use `![description](/assets/picture.png)`.
- I write the post in whatever language I feel like. the homepage preview shows it the same in both versions.
- I avoid writing double curly braces or {% raw %}`{%`{% endraw %} in posts, because Jekyll treats them as template code (this very line broke the build the first time). if I really need them, I wrap that bit in `raw` / `endraw` tags.
- to preview locally before pushing:

  ```sh
  docker run --rm -it -p 4000:4000 -v "$PWD":/srv/jekyll jekyll/jekyll:4 jekyll serve
  ```

  then I open <http://localhost:4000>.

that's it. now go write something, maru.
