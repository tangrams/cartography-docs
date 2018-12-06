# Themes

**Like a basemap style but want something just a little different?**

Some styles are available in range of **label** steps, **color** palettes, and levels of **detail**. This section describes the options and shows how to import them.

### Managing imports

Order matters when importing Tangram YAML files. First import the basemap style, then import themes.

**NOTE:** You'll need to fully qualify the URL for each import as imports are relative to the Tangram scene file's base URL (not the first import's base URL).

Example **Tangram YAML** usage:

```
import:
    # basemap style
    - https://www.nextzen.org/carto/refill-style/12/refill-style.zip
    # recolor basemap style with a theme color
    - https://www.nextzen.org/carto/refill-style/12/themes/color-pink-yellow.zip
    # add more labels
    - https://www.nextzen.org/carto/refill-style/12/themes/label-10.zip
    # other imports to taste...
```

_NOTE: As Mapzen's basemaps are still in active development we recommend pegging an import to a specific **MAJOR** version, e.g.: `8`, so you enjoy any minor and patch updates but are ensured of stable named scene elements._

Example **Tangram JS** usage:

```
var layer = Tangram.leafletLayer({
        scene: {
          import: [
            'https://www.nextzen.org/carto/refill-style/12/refill-style.zip',
            'https://www.nextzen.org/carto/refill-style/12/themes/color-pink-yellow.zip',
            'https://www.nextzen.org/carto/refill-style/12/themes/label-10.zip'],
          global: { 'sdk_mapzen_api_key': 'your-mapzen-api-key' } },
        attribution: '<a href="https://www.nextzen.org/tangram" target="_blank">Tangram</a>, &copy; OSM contributors'
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
        'https://www.nextzen.org/carto/refill-style/12/refill-style.zip',
        'https://www.nextzen.org/carto/refill-style/12/themes/color-pink-yellow.zip'
        'https://www.nextzen.org/carto/refill-style/12/themes/label-10.zip'
      ] } }
});
```

## Bubble Wrap

The Bubble Wrap style supports 1 theme option: **label**.

### Label

Bubble Wrap includes **12 label steps**, **0 to 11**. **11** at the top most level displays all, while **0** displays none.

Current **MAJOR** versioned releases:

| label  | note            | import
|-------:|-----------------|--------------------------------------------------------------
| 0      | **no-labels**   | `https://www.nextzen.org/carto/bubble-wrap-style/10/themes/label-0.zip`
| 1      |                 | `https://www.nextzen.org/carto/bubble-wrap-style/10/themes/label-1.zip`
| 2      |                 | `https://www.nextzen.org/carto/bubble-wrap-style/10/themes/label-2.zip`
| 3      |                 | `https://www.nextzen.org/carto/bubble-wrap-style/10/themes/label-3.zip`
| 4      |                 | `https://www.nextzen.org/carto/bubble-wrap-style/10/themes/label-4.zip`
| 5      | _default_       | `https://www.nextzen.org/carto/bubble-wrap-style/10/themes/label-5.zip`
| 6      |                 | `https://www.nextzen.org/carto/bubble-wrap-style/10/themes/label-6.zip`
| 7      |                 | `https://www.nextzen.org/carto/bubble-wrap-style/10/themes/label-7.zip`
| 8      |                 | `https://www.nextzen.org/carto/bubble-wrap-style/10/themes/label-8.zip`
| 9      |                 | `https://www.nextzen.org/carto/bubble-wrap-style/10/themes/label-9.zip`
| 10     | **more-labels** | `https://www.nextzen.org/carto/bubble-wrap-style/10/themes/label-10.zip`
| 11     |                 | `https://www.nextzen.org/carto/bubble-wrap-style/10/themes/label-11.zip`

## Cinnabar

The Cinnabar style supports 1 theme option: **label**.

### Label

Cinnabar includes **12 label steps**, **0 to 11**. **11** at the top most level displays all, while **0** displays none.

Current **MAJOR** versioned releases:

| label  | note            | import
|-------:|-----------------|--------------------------------------------------------------
| 0      | **no-labels**   | `https://www.nextzen.org/carto/cinnabar-style/10/themes/label-0.zip`
| 1      |                 | `https://www.nextzen.org/carto/cinnabar-style/10/themes/label-1.zip`
| 2      |                 | `https://www.nextzen.org/carto/cinnabar-style/10/themes/label-2.zip`
| 3      |                 | `https://www.nextzen.org/carto/cinnabar-style/10/themes/label-3.zip`
| 4      |                 | `https://www.nextzen.org/carto/cinnabar-style/10/themes/label-4.zip`
| 5      | _default_       | `https://www.nextzen.org/carto/cinnabar-style/10/themes/label-5.zip`
| 6      |                 | `https://www.nextzen.org/carto/cinnabar-style/10/themes/label-6.zip`
| 7      |                 | `https://www.nextzen.org/carto/cinnabar-style/10/themes/label-7.zip`
| 8      |                 | `https://www.nextzen.org/carto/cinnabar-style/10/themes/label-8.zip`
| 9      |                 | `https://www.nextzen.org/carto/cinnabar-style/10/themes/label-9.zip`
| 10     | **more-labels** | `https://www.nextzen.org/carto/cinnabar-style/10/themes/label-10.zip`
| 11     |                 | `https://www.nextzen.org/carto/cinnabar-style/10/themes/label-11.zip`

## Refill

Refill Style supports 3 different theme options: **color**, **label**, and **detail**.

### Color

Refill includes color variations on black and white, starting with **high-contrast**, original **default**, and **gray**. High-Contrast is basic and minimal, and great for printing.

For data visualization purposes gray and several other muted color themes are including single color series in **blue**, **sepia**, and **pink**. Two-color series includes **pink-yellow**, **brown-orange**, and **blue-gray**. We've also migrated the old standalone basemap style Zinc to be a **zinc** Refill color theme.

The dark series includes **inverted**, **purple-green**, and **gray-gold**.

<img src="../img/refill/refill-theme-mallorca_bw.jpg" width=780>

<img src="../img/refill/refill-theme-mallorca_color.jpg" width=780>

<img src="../img/refill/refill-theme-mallorca_2color.jpg" width=780>

<img src="../img/refill/refill-theme-mallorca_dark.jpg" width=780>

Current **MAJOR** versioned releases:

| color         | note      | import
|:--------------|-----------|------------------------------------------------------------
| black         | _default_ | `https://www.nextzen.org/carto/refill-style/12/themes/color-black.zip`
| blue          |           | `https://www.nextzen.org/carto/refill-style/12/themes/color-blue.zip`
| blue-gray     |           | `https://www.nextzen.org/carto/refill-style/12/themes/color-blue-gray.zip`
| brown-orange  |           | `https://www.nextzen.org/carto/refill-style/12/themes/color-brown-orange.zip`
| gray          |           | `https://www.nextzen.org/carto/refill-style/12/themes/color-gray.zip`
| gray-gold     |           | `https://www.nextzen.org/carto/refill-style/12/themes/color-gray-gold.zip`
| high-contrast |           | `https://www.nextzen.org/carto/refill-style/12/themes/color-high-contrast.zip`
| inverted      |           | `https://www.nextzen.org/carto/refill-style/12/themes/color-inverted.zip`
| pink          |           | `https://www.nextzen.org/carto/refill-style/12/themes/color-pink.zip`
| pink-yellow   |           | `https://www.nextzen.org/carto/refill-style/12/themes/color-pink-yellow.zip`
| purple-green  |           | `https://www.nextzen.org/carto/refill-style/12/themes/color-purple-green.zip`
| sepia         |           | `https://www.nextzen.org/carto/refill-style/12/themes/color-sepia.zip`
| zinc         |           | `https://www.nextzen.org/carto/refill-style/12/themes/color-zinc.zip`

### Label

Refill includes **12 label steps**, **0 to 11**. **11** at the top most level displays all, while **0** displays none.

<img src="../img/refill/refill-themes-label.jpg" width=780>


Current **MAJOR** versioned releases:

| label  | note            | import
|-------:|-----------------|------------------------------------------------------------
| 0      | **no-labels**   | `https://www.nextzen.org/carto/refill-style/12/themes/label-0.zip`
| 1      |                 | `https://www.nextzen.org/carto/refill-style/12/themes/label-1.zip`
| 2      |                 | `https://www.nextzen.org/carto/refill-style/12/themes/label-2.zip`
| 3      |                 | `https://www.nextzen.org/carto/refill-style/12/themes/label-3.zip`
| 4      |                 | `https://www.nextzen.org/carto/refill-style/12/themes/label-4.zip`
| 5      | _default_       | `https://www.nextzen.org/carto/refill-style/12/themes/label-5.zip`
| 6      |                 | `https://www.nextzen.org/carto/refill-style/12/themes/label-6.zip`
| 7      |                 | `https://www.nextzen.org/carto/refill-style/12/themes/label-7.zip`
| 8      |                 | `https://www.nextzen.org/carto/refill-style/12/themes/label-8.zip`
| 9      |                 | `https://www.nextzen.org/carto/refill-style/12/themes/label-9.zip`
| 10     | **more-labels** | `https://www.nextzen.org/carto/refill-style/12/themes/label-10.zip`
| 11     |                 | `https://www.nextzen.org/carto/refill-style/12/themes/label-11.zip`


### Detail

Refill includes **12 levels of detail**, **0 to 11**. **11** at the top most level displays all. **0** starts with *water* and *earth*. *Water boundaries* start at **detail-2**. *Roads* begin at **detail-3**, starting with *highways*. *Major roads* and *place labels* appear at **detail-4** and gradually build up as you go further up the levels. The original Refill style is set to **detail-10** (default).

Although some levels are clear-cut as to what's visible, each Level of Detail is never static, all LOD's show more detail accordingly as you zoom in.

<img src="../img/refill/refill-themes-detail.jpg" width=780>

Current **MAJOR** versioned releases:

| detail | note      | import
|-------:|-----------|-------------------------------------------------------------
| 0      |           | `https://www.nextzen.org/carto/refill-style/12/themes/detail-0.zip`
| 1      |           | `https://www.nextzen.org/carto/refill-style/12/themes/detail-1.zip`
| 2      |           | `https://www.nextzen.org/carto/refill-style/12/themes/detail-2.zip`
| 3      |           | `https://www.nextzen.org/carto/refill-style/12/themes/detail-3.zip`
| 4      |           | `https://www.nextzen.org/carto/refill-style/12/themes/detail-4.zip`
| 5      |           | `https://www.nextzen.org/carto/refill-style/12/themes/detail-5.zip`
| 6      |           | `https://www.nextzen.org/carto/refill-style/12/themes/detail-6.zip`
| 7      |           | `https://www.nextzen.org/carto/refill-style/12/themes/detail-7.zip`
| 8      |           | `https://www.nextzen.org/carto/refill-style/12/themes/detail-8.zip`
| 9      |           | `https://www.nextzen.org/carto/refill-style/12/themes/detail-9.zip`
| 10     | _default_ | `https://www.nextzen.org/carto/refill-style/12/themes/detail-10.zip`
| 11     |           | `https://www.nextzen.org/carto/refill-style/12/themes/detail-11.zip`

## Tron

The Tron style supports 1 theme option: **label**.

### Label

Tron includes **12 label steps**, **0 to 11**. **11** at the top most level displays all, while **0** displays none.

Current **MAJOR** versioned releases:

| label  | note            | import
|-------:|-----------------|--------------------------------------------------------------
| 0      | **no-labels**   | `https://www.nextzen.org/carto/tron-style/6/themes/label-0.zip`
| 1      |                 | `https://www.nextzen.org/carto/tron-style/6/themes/label-1.zip`
| 2      |                 | `https://www.nextzen.org/carto/tron-style/6/themes/label-2.zip`
| 3      |                 | `https://www.nextzen.org/carto/tron-style/6/themes/label-3.zip`
| 4      |                 | `https://www.nextzen.org/carto/tron-style/6/themes/label-4.zip`
| 5      | _default_       | `https://www.nextzen.org/carto/tron-style/6/themes/label-5.zip`
| 6      |                 | `https://www.nextzen.org/carto/tron-style/6/themes/label-6.zip`
| 7      |                 | `https://www.nextzen.org/carto/tron-style/6/themes/label-7.zip`
| 8      |                 | `https://www.nextzen.org/carto/tron-style/6/themes/label-8.zip`
| 9      |                 | `https://www.nextzen.org/carto/tron-style/6/themes/label-9.zip`
| 10     | **more-labels** | `https://www.nextzen.org/carto/tron-style/6/themes/label-10.zip`
| 11     |                 | `https://www.nextzen.org/carto/tron-style/6/themes/label-11.zip`

## Walkabout

The Walkabout style supports 1 theme option: **label**.

### Label

Walkabout includes **12 label steps**, **0 to 11**. **11** at the top most level displays all, while **0** displays none.

Current **MAJOR** versioned releases:

| label  | note            | import
|-------:|-----------------|--------------------------------------------------------------
| 0      | **no-labels**   | `https://www.nextzen.org/carto/walkabout-style/8/themes/label-0.zip`
| 1      |                 | `https://www.nextzen.org/carto/walkabout-style/8/themes/label-1.zip`
| 2      |                 | `https://www.nextzen.org/carto/walkabout-style/8/themes/label-2.zip`
| 3      |                 | `https://www.nextzen.org/carto/walkabout-style/8/themes/label-3.zip`
| 4      |                 | `https://www.nextzen.org/carto/walkabout-style/8/themes/label-4.zip`
| 5      | _default_       | `https://www.nextzen.org/carto/walkabout-style/8/themes/label-5.zip`
| 6      |                 | `https://www.nextzen.org/carto/walkabout-style/8/themes/label-6.zip`
| 7      |                 | `https://www.nextzen.org/carto/walkabout-style/8/themes/label-7.zip`
| 8      |                 | `https://www.nextzen.org/carto/walkabout-style/8/themes/label-8.zip`
| 9      |                 | `https://www.nextzen.org/carto/walkabout-style/8/themes/label-9.zip`
| 10     | **more-labels** | `https://www.nextzen.org/carto/walkabout-style/8/themes/label-10.zip`
| 11     |                 | `https://www.nextzen.org/carto/walkabout-style/8/themes/label-11.zip`
