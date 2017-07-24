# Themes

**Like a basemap style but want something just a little different?**

Some styles are available in range of **color** palettes, **label** steps, and levels of **detail**. This section describes the options and shows how to import them.

Managing imports

Order matters when importing Tangram YAML files. First import the basemap style, then import themes.

**NOTE:** You'll need to fully qualify the URL for each import as imports are relative to the Tangram scene file's base URL (not the first import's base URL).

Example **Tangram YAML** usage:

```
import:
    # basemap style
    - https://mapzen.com/carto/refill-style/8/refill-style.zip
    # recolor basemap style with a theme color
    - https://mapzen.com/carto/refill-style/8/themes/color-pink-yellow.zip
    # other imports to taste...
```

_NOTE: As Mapzen's basemaps are still in active development we recommend pegging an import to a specific **MAJOR** version, e.g.: `8`, so you enjoy any minor and patch updates but are ensured of stable named scene elements._

Example **Tangram JS** usage:

```
var layer = Tangram.leafletLayer({
        scene: {
          import: [
            'https://mapzen.com/carto/refill-style/8/refill-style.zip',
            'https://mapzen.com/carto/refill-style/8/themes/color-pink-yellow.zip'],
          global: { 'sdk_mapzen_api_key': 'your-mapzen-api-key' } },
        attribution: '<a href="https://mapzen.com/tangram" target="_blank">Tangram</a>, &copy; OSM contributors'
    });
```

Example **mapzen.js** usage:

```
L.Mapzen.apiKey = 'your-mapzen-api-key';

var map = L.Mapzen.map('map', {
  center: [40.8041, -124.1506],
  zoom: 15,
  maxZoom: 20,
  tangramOptions: {
    scene: {
      import: [
        'https://mapzen.com/carto/refill-style/8/refill-style.zip',
        'https://mapzen.com/carto/refill-style/8/themes/color-pink-yellow.zip'
      ] } }
});
```

## Refill

Refill Style supports 3 different theme options: **color**, **label**, and **detail**.

### Color

Refill includes color variations on black and white, starting with **high-contrast**, original **default**, and **gray**. High-Contrast is basic and minimal, and great for printing.

For data visualization purposes gray and several other muted color themes are including single color series in **blue**, **sepia**, and **pink**. Two-color series includes **pink-yellow**, **brown-orange**, and **blue-gray**.

The dark series includes **inverted**, **purple-green**, and **gray-gold**.

<img src="../img/refill/refill-theme-mallorca_bw.jpg" width=780>

<img src="../img/refill/refill-theme-mallorca_color.jpg" width=780>

<img src="../img/refill/refill-theme-mallorca_2color.jpg" width=780>

<img src="../img/refill/refill-theme-mallorca_dark.jpg" width=780>

Current **MAJOR** versioned releases:

| color         | note      | import
|:--------------|-----------|------------------------------------------------------------
| black         | _default_ | `https://mapzen.com/carto/refill-style/8/themes/color-black.zip`
| blue          |           | `https://mapzen.com/carto/refill-style/8/themes/color-blue.zip`
| blue-gray     |           | `https://mapzen.com/carto/refill-style/8/themes/color-blue-gray.zip`
| brown-orange  |           | `https://mapzen.com/carto/refill-style/8/themes/color-brown-orange.zip`
| gray          |           | `https://mapzen.com/carto/refill-style/8/themes/color-gray.zip`
| gray-gold     |           | `https://mapzen.com/carto/refill-style/8/themes/color-gray-gold.zip`
| high-contrast |           | `https://mapzen.com/carto/refill-style/8/themes/color-high-contrast.zip`
| inverted      |           | `https://mapzen.com/carto/refill-style/8/themes/color-inverted.zip`
| pink          |           | `https://mapzen.com/carto/refill-style/8/themes/color-pink.zip`
| pink-yellow   |           | `https://mapzen.com/carto/refill-style/8/themes/color-pink-yellow.zip`
| purple-green  |           | `https://mapzen.com/carto/refill-style/8/themes/color-purple-green.zip`
| sepia         |           | `https://mapzen.com/carto/refill-style/8/themes/color-sepia.zip`

### Label

Refill includes **12 Levels of Labels**, **0 to 11**. **11** at the top most level displays all, while **0** displays none. 

Starting with version 8 of Refill Mapzen recommends to import the default `refill-style` and then add or remove labels by importing a **label** theme.

Mapping of Refill label variants in version 7 and earlier releases to new theme-based label steps:

| Refill label variant       | label |
|----------------------------|------:|
| `refill-style` _(default)_ | 5     |
| `refill-style-no-labels`   | 0     |
| `refill-style-more-labels` | 10    |

The two named Refill label variants `refill-style-no-labels` or `refill-style-more-labels` available in version 7 ane earlier are no longer supported directly – you need up upgrade to version 8 and import the label theme.

<img src="../img/refill/refill-theme-label.jpg" width=780>


Current **MAJOR** versioned releases:

| label  | note            | import
|-------:|-----------------|------------------------------------------------------------
| 0      | **no-labels**   | `https://mapzen.com/carto/refill-style/8/themes/label-0.zip`
| 1      |                 | `https://mapzen.com/carto/refill-style/8/themes/label-1.zip`
| 2      |                 | `https://mapzen.com/carto/refill-style/8/themes/label-2.zip`
| 3      |                 | `https://mapzen.com/carto/refill-style/8/themes/label-3.zip`
| 4      |                 | `https://mapzen.com/carto/refill-style/8/themes/label-4.zip`
| 5      | _default_       | `https://mapzen.com/carto/refill-style/8/themes/label-5.zip`
| 6      |                 | `https://mapzen.com/carto/refill-style/8/themes/label-6.zip`
| 7      |                 | `https://mapzen.com/carto/refill-style/8/themes/label-7.zip`
| 8      |                 | `https://mapzen.com/carto/refill-style/8/themes/label-8.zip`
| 9      |                 | `https://mapzen.com/carto/refill-style/8/themes/label-9.zip`
| 10     | **more-labels** | `https://mapzen.com/carto/refill-style/8/themes/label-10.zip`
| 11     |                 | `https://mapzen.com/carto/refill-style/8/themes/label-11.zip`


### Detail

Refill includes **12 levels of detail**, **0 to 11**. **11** at the top most level displays all. **0** starts with *water* and *earth*. *Water boundaries* start at **detail-2**. *Roads* begin at **detail-3**, starting with *highways*. *Major roads* and *place labels* appear at **detail-4** and gradually build up as you go further up the levels. The original Refill style is set to **detail-10** (default). 

Although some levels are clear-cut as to what's visible, each Level of Detail is never static, all LOD's show more detail accordingly as you zoom in.

<img src="../img/refill/refill-theme-detail.jpg" width=780>


Current **MAJOR** versioned releases:

| detail | note      | import
|-------:|-----------|------------------------------------------------------------
| 0      |           | `https://mapzen.com/carto/refill-style/8/themes/detail-0.zip`
| 1      |           | `https://mapzen.com/carto/refill-style/8/themes/detail-1.zip`
| 2      |           | `https://mapzen.com/carto/refill-style/8/themes/detail-2.zip`
| 3      |           | `https://mapzen.com/carto/refill-style/8/themes/detail-3.zip`
| 4      |           | `https://mapzen.com/carto/refill-style/8/themes/detail-4.zip`
| 5      |           | `https://mapzen.com/carto/refill-style/8/themes/detail-5.zip`
| 6      |           | `https://mapzen.com/carto/refill-style/8/themes/detail-6.zip`
| 7      |           | `https://mapzen.com/carto/refill-style/8/themes/detail-7.zip`
| 8      |           | `https://mapzen.com/carto/refill-style/8/themes/detail-8.zip`
| 9      |           | `https://mapzen.com/carto/refill-style/8/themes/detail-9.zip`
| 10     | _default_ | `https://mapzen.com/carto/refill-style/8/themes/detail-10.zip`
| 11     |           | `https://mapzen.com/carto/refill-style/8/themes/detail-11.zip`
