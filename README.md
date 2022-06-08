# (Brief) instructions for editing the CinC 2023 website

We are using the [Minimal Mistakes](https://mmistakes.github.io/minimal-mistakes/) GitHub Pages/Jekyll/Kramdown theme for the CinC 2023 website. I edited this theme, which is (probably) mostly used for blogs and similar websites. Please see the following guidance for editing and viewing the website.

## Updating the website

### Changing pages

Add or edit a Markdown file in the `pages` folder to add or edit a webpage. For example, add the following text to a file `/pages/example.md`:

    ---
    title: "An Example Page"
    layout: single
    author_profile: true
    permalink: /example/
    ---

    Hello, world.

The webpage will appear at [https://cinc2023.org/example/](https://cinc2023.org/example/). The title will be "An Example Page", and the body will be "Hello, world."

### Links

__Always__ use relative links instead of absolute links to link to other pages or images on the site.

For example, if we are on `https://cinc2023.org/` and want to add a link to `https://cinc2023.org/example/`, then write something like `[link](/example/)` to the home page instead of `[link](https://cinc2023.org/example/)`.

For another example, if we are on `https://cinc2023.org/here/` and want to add a link to `https://cinc2023.org/there/`, then write something like `[link](../there/)` to `/here/` instead of `[link](https://cinc2023.org/there/)`.

### Changing images and other files

Place an image in `/assets/img/` and display it by adding `![Example](/assets/img/example.svg)` to the Markdown file where you want the image to appear. Check online for how to modify image size, positioning, etc. in Kramdown.

Advice: Use SVG for vector images, PNG for screenshots, and JPG for photographs. We can convert PDFs to SVGs as needed. Always use relative links (see below) instead of absolute links.

### LaTeX

I edited the `/_includes/scripts.html` file to add LaTeX support:

    <script type="text/javascript" async src="https://cdnjs.cloudflare.com/ajax/libs/mathjax/2.7.7/latest.js?config=TeX-MML-AM_CHTML"> </script>

You can add equations by writing something like `$$\int_0^\infty \exp{-x^2} dx = \frac{\sqrt{\pi}}{2}$$`. Note that two dollar signs are needed here instead of the usual single dollar sign because dollar signs are common on websites and we don't want to need to escape them.

### Side, navigation/top bar, website globals, etc.

### Sidebar, website globals, etc.

Edit `_config.yml` to edit the side bar.. This file controls much more than the sidebar. Be careful.

Edit `_data/navigation.yml` to edit the top/nagivation bar. Check the other entries for examples.

## Previewing the website locally

__Please__ preview the website locally before updating anything on GitHub.

To preview the website locally, run

    bundle install
    bundle update

in your terminal to install the necessary packages, run

    bundle exec jekyll serve

in your terminal to serve the website locally, and navigate to `localhost:4000` in your browser to view the website.

You will probably need to install several dependancies for the local preview to work for the first time. Try reading this [page](https://docs.github.com/en/pages/setting-up-a-github-pages-site-with-jekyll/testing-your-github-pages-site-locally-with-jekyll) and search for the errors online.

You can edit the pages (see above) and refresh your browser to immediately see your updates, but you need to restart `bundle exec jekyll serve` every time you edit the `_config.yml` to see your changes.

## Update the website

__Please__ view the website locally before updating anything on GitHub.

You can use the usual `git pull`, `git add`, `git commit`, `git push` commands to push changes to GitHub. Remember to pull changes before you push changes.

You can also upload files through your browser, but you are responsible for checking for conflicts, i.e., the file was updated after you downloaded it but before you uploaded it again.
