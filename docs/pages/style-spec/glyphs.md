---
title: Glyphs
id: glyphs
description: A style's glyphs property provides a URL template for loading signed-distance-field glyph sets in PBF format.
contentType: specification
prependJs:
    - "import ref from '../../../mapbox-gl-js/src/style-spec/reference/latest';"
---

A style's `glyphs` property provides a URL template for loading signed-distance-field glyph sets in PBF format.

```json
"glyphs": {{JSON.stringify(
    ref.$root.glyphs.example,
    null,
    2
)}}
```

This URL template should include two tokens:

- <code>{`{fontstack}`}</code> When requesting glyphs, this token is replaced with a comma separated list of fonts from a font stack specified in the [`text-font`](#layout-symbol-text-font) property of a symbol layer.
- <code>{`{range}`}</code> When requesting glyphs, this token is replaced with a range of 256 Unicode code points. For example, to load glyphs for the [Unicode Basic Latin and Basic Latin-1 Supplement blocks](https://en.wikipedia.org/wiki/Unicode_block), the range would be `0-255`. The actual ranges that are loaded are determined at runtime based on what text needs to be displayed.
