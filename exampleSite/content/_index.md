---
title: "Hugo module for retrieving, processing, and placing images"
resources:
  - src: mulyadi-JJMoAiVl9jA-unsplash.jpg
    name: splash
    title: Splash!
    params:
      alt: Splashing drop of water
      width: full
      rel: nofollow
      hint: graphic
---

The example site demonstrates the functionality of the module with simple layout examples. The full power of the module unfolds when we use it in a project to offer users a great variety of layout options with Markdown attributes. The module includes no CSS files but we need to register the available CSS classes in the configuration (data/hugoModImg) to check the user input.

## Image sources

There are three options for Hugo to retrieve images: **Page bundles**, the **site-wide** assets folder, and **remote** servers via absolute URLs.

Because we can’t add much information in the Markdown image tag, this module processes extra information from local (!) data structures: Hugo’s front-matter resources and **data** files.

### Page bundles

![](splash)

### Site-wide (global asset folder)

![Splash of water](erda-estremera-eMX1aIAp9Nw-unsplash.jpg)

### Remote (URL)

Remote images are cached and processed locally.

![Random image from picsum](https://picsum.photos/1200/500)

### Data (indirect)

A data file in the format YAML, TOML, or JSON needs to include a source like the previous ones. We can use such a file to add local meta-data to global or remote images.

#### Global source in data file

![Global image via data file](global.yaml)

#### Remote source in data file

![Remote image via data file](remote.json)

## Missing image

To prevent broken image tags the module always provides a placeholder for missing ones:

![Missing](missing.jpg)
{#missing}