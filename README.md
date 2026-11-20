# lizzybrooks.org

A plain HTML version of Lizzy Brooks's portfolio, ready for GitHub Pages. There is no build step: every page is an ordinary `.html` file, and all styling lives in `style.css`.

## 1. Bring the images over (once)

The pages point to images in the `images/` folder, which starts empty. While the old WordPress site is still online, run this from inside the site folder (Mac or Linux Terminal):

```
bash download-images.sh
```

It copies all 99 images into `images/` and names them by project (`images/sense-system/01.jpg`, and so on). If any fail, it lists them, and you can save those by hand from the old site to the file name shown in the script.

## 2. Put it on GitHub Pages

1. Create a new repository on GitHub. Naming it `yourusername.github.io` makes the site live at `https://yourusername.github.io/`; any other name puts it at `https://yourusername.github.io/reponame/`. Both work.
2. Upload everything in this folder (including the `images/` folder and the hidden `.nojekyll` file) to the repository.
3. In the repository, go to **Settings → Pages**, set **Source** to "Deploy from a branch", pick `main` and `/ (root)`, and save. The site appears within a minute or two.

## 3. Point lizzybrooks.org at it (optional)

In **Settings → Pages → Custom domain**, enter `www.lizzybrooks.org` and save (GitHub adds a `CNAME` file for you). Then, at your domain registrar, add a `CNAME` record for `www` pointing to `yourusername.github.io`, plus the four `A` records for the bare domain that GitHub lists in its docs ("Managing a custom domain for your GitHub Pages site"). Tick **Enforce HTTPS** once it becomes available.

The folder names match the old WordPress addresses (`/sense-system/`, `/photography/`, and so on), so existing links to your projects keep working. The old `/about-2/` address redirects to the new `/about/`.

## Editing

- **Change text:** open the project's `index.html` (for example `kibuki/index.html`) and edit the words between `<p class="prose">` and `</p>`.
- **Add an image:** put the file in that project's images folder and copy an existing `<figure>` line. Images inside one `<div class="row">` sit side by side at the same height; the `flex:` number on each figure is its width divided by its height.
- **Add a video:** copy a `<div class="video">` block and swap in the YouTube or Vimeo embed address.
- **Add a project:** copy an existing project folder, rename it, edit it, then add a link to it in the menu list of every page (the `<ul class="projects">` near the top).
- **Image descriptions:** each image has placeholder alt text like "Penumbra, image 4". Replacing these with short descriptions helps visitors using screen readers.
- **Colors and fonts:** change the values at the top of `style.css`.
