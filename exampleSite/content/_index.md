---
title: "Hugo module for retrieving, processing, and placing images"
---

## Image sources

There are three types of image sources Hugo can retrieve: **Local** images in page bundles, **global** (site-wide) images in the assets folder, and **remote** images via absolute URLs.

Because we can only add a very limited amount of information in the Markdown image tag, this module additionally offers to parse **data** files to process layout information and generate a caption.

### Local (page bundle)

![Local](mulyadi-JJMoAiVl9jA-unsplash.jpg)

### Global (asset folder)

![Global](erda-estremera-eMX1aIAp9Nw-unsplash.jpg)

### Remote (URL)

Remote images are cached and processed locally.

![Picsum](https://picsum.photos/1200/500)

### Data (indirect)

A data file in the format YAML, TOML, or JSON needs to include a source like the previous ones. We can use such a file to add local meta-data to global or remote images.

#### Global source in data file

![Global image via data file](global.yaml)

#### Remote source in data file

![Remote image via data file](remote.json)

## Missing image

To prevent broken image tags the module always provides a placeholder for missing ones:

![missing image](missing.jpg)