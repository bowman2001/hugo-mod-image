---
title: "Hugo module for retrieving, processing, and placing images"
resources:
  - src: mulyadi-JJMoAiVl9jA-unsplash.jpg
    name: splash
    params:
      alt: Splashing drop of water
      width: full
      link: https://unsplash.com/photos/JJMoAiVl9jA
      rel: nofollow
      target: _blank
      hint: graphic
---

The example site demonstrates the functionality of the module with simple layout examples. The full power of the module unfolds when we use it in a project to offer users a variety of layout options.

The module does **not** include CSS files (only the example site does). However, we need to register our available CSS classes in the configuration (data/hugoModImg) to check the user input.

## Image sources

There are three options for Hugo to retrieve images: **Page bundles**, the **site-wide** assets folder, and **remote** servers via absolute URLs.

Because we can’t add much information in the Markdown image tag, this module processes extra information from local (!) data structures: Hugo’s front-matter resources and image-specific **data** files.

### Page bundles

![](splash "What a splash!")

### Site-wide (global asset folder)

![Splash of water](erda-estremera-eMX1aIAp9Nw-unsplash.jpg)

### Remote (URL)

Remote images are cached and processed locally.

![Random image from picsum](https://picsum.photos/1200/500)
{.attr-test}

### Data (indirect)

A data file in the format YAML, TOML, or JSON needs to include a source like the previous ones. We can use such a file to add local parameters to site-wide or remote images without resource information.

#### Site-wide source in data file

![Global image via data file](global.yaml?w=half)

#### Remote source in data file

![Remote image via data file](remote.json?w=full)

## Embedded images

![](splash?w=quarter&posh=left) {{% pangram 10 %}} 
## Missing image

To prevent broken image tags the module always provides a placeholder for missing ones:

![Missing](missing.jpg)
{#missing}