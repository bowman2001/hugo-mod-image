---
title: "Hugo module for retrieving, processing, and placing images"
resources:
  - src: mulyadi-JJMoAiVl9jA-unsplash.jpg
    name: splash
    params:
      alt: Splashing drop of water
      link: https://unsplash.com
      rel: nofollow
      target: _blank
      caption: Embedded with link
      lqip: run
  - src: Png-logo.png
    name: png
    params:
      caption: Unofficial PNG logo
      padding: one
      background: light
      box: shadow
      type: contain
      hint: icon
      lqip: run
      id: png
  - src: Perplex.svg
    name: perplex
    params:
      alt: Perplex logo
      attr: Perplex theme
      attrLink: https://perplex.desider.at
      target: _blank
      caption: Perplex logo
      padding: one
      background: light
      box: shadow
      type: contain
  - src: small_portrait.jpg
    name: portrait
    params:
      alt: Georg Makowski
---

The example site demonstrates the functionality of the module with simple layout examples. The full power of the module unfolds when we use it in a project to offer users a variety of formatting and styling options with HTML attributes.

The module injects CSS classes from user input but does **not** ship with CSS files (only the example site does). The optional classes need to be registered in the configuration (data/hugoModImg).

## Image sources

There are three options for Hugo to retrieve images: **Page bundles**, the **site-wide** assets folder, and **remote** servers via absolute URLs. They are all checked to give users maximum flexibility.

Because the Markdown image tag can’t hold much information, users need to add it elsewhere. This module collects associated information from local data structures: Hugo’s **front-matter resources** and image-specific **data** files. All data is temporarily stored in a parameter map.

The included image render hook can produce figures and embedded images with linked images and a caption.

(The alternative to the universal image hook is to provide shortcodes for specific image formats. They can use a subset of the available data collection functions and rendering templates.)  

### Page bundles

![](splash?posh=left&zoom=1.3 "What a splash!") {{% pangram 11 %}}

### Site-wide (global asset folder)

![Splash of water](erda-estremera-eMX1aIAp9Nw-unsplash.jpg?posh=right) {{% pangram 11 %}}

### Remote (URL)

Remote images are cached and processed locally. The only way to add attributes here are Markdown attributes. And they are only available for stand-alone images (figure).

![Random image from picsum](https://picsum.photos/id/599/1200/500)

### Data (indirect)

A data file in the format YAML, TOML, or JSON needs to include a source like the previous ones. We can use such a file to add local parameters to site-wide or remote images without resource information.

#### A site-wide source in a data file

![Global image in a data file](global) {{% pangram 11 %}}

#### Remote source in a data file

![Remote image in a data file](remote?w=full)

## Preprocessing

### Rotate

![Splash](rotate.yaml)

### Change ratio

![Splash](ratio)

### Zoom

![Splash](zoom.yaml)

### Rotate, zoom and change ratio

![Splash](rotate-zoom-ratio)

## Lossless

### PNG

![PNG](png)

### SVG

![Perplex logo](perplex)

## Missing image

To prevent broken image tags the module always provides a placeholder for missing ones:

![Missing](test-missing)
{#missing}

## Kroki diagrams

```kroki {diagram=BlockDiag background=light caption="Block diagram" attr="Kroki.io" attrlink="https://kroki.io"}
blockdiag {
  Kroki -> generates -> "Block diagrams";
  Kroki -> is -> "very easy!";

  Kroki [color = "greenyellow"];
  "Block diagrams" [color = "pink"];
  "very easy!" [color = "orange"];
}
```

```kroki {diagram=BlockDiag background=light caption="Missing diagram" attr="Kroki.io" attrlink="https://kroki.io"}
```

## Included shortcodes

### Print the recommended size for images

When we have configured the width of our image classes, we want to inform users about the necessary image width.

| Class | Min. width            | Max. width                  |
|:-- | :-------------------- | :-------------------------- |
| Tiny |{{% mod-img/width "tiny" 1 %}} | {{% mod-img/width "tiny" %}} |
| Small |{{% mod-img/width "full" 1 %}} | {{% mod-img/width "full" %}} |
| Double |{{% mod-img/width "double" 1 %}} | {{% mod-img/width "double" %}} |

### Print other configuration parameters

| Parameter | Options                                                    |
| :-------- | :--------------------------------------------------------- |
| width     | _figure_: {{% mod-img/value "figure" "width" "options" %}} |
|           | _embed_:  {{% mod-img/value "embed" "width" "options" %}}  |
|           |                                                            |