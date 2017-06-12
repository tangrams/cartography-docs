# Themes

**Like a basemap style but want something just a little different?** 

Some styles are available in a range of colors and other options. This section describes the options and shows how to import them.

#### Managing imports

Order matters when importing Tangram YAML files. First import the basemap style, then import themes.

**NOTE:** You'll need to fully qualify the URL for each import as imports are relative to the Tangram scene file's base URL (not the first import's base URL).

Example **Tangram YAML** usage:

```
import:
    # basemap style
    - https://mapzen.com/carto/refill-style/7/refill-style.zip
    # recolor basemap style with a theme color
    - https://mapzen.com/carto/refill-style/7/themes/pink-yellow.zip
    # other imports to taste...
```

_NOTE: As Mapzen's basemaps are still in active development we recommend pegging an import to a specific **MAJOR** version, eg: `7`, so you enjoy any minor and patch updates but are ensured of stable named scene elements._

Example **Tangram JS** usage:

```
var layer = Tangram.leafletLayer({
        scene: { 
          import: [
            'https://mapzen.com/carto/refill-style/7/refill-style.zip', 
            'https://mapzen.com/carto/refill-style/7/themes/pink-yellow.zip'],
          global: { 'sdk_mapzen_api_key': 'mapzen-xxxxxx' } },
        attribution: '<a href="https://mapzen.com/tangram" target="_blank">Tangram</a>, &copy; OSM contributors'
    });
```

## Refill

### Color

Refill includes color variations on black and white, starting with **high-contrast**, original **default**, and **gray**. High-Contrast is basic and minimal, and great for printing.

For data visualization purposes gray and several other muted color themes are includeing single color series in **blue**, **sepia**, and **pink**. Two-color series includes **pink-yellow**, **brown-orange**, and **blue-gray**.

<img src="img/refill/refill-theme-mallorca_bw.jpg" width=780 height=270>

<img src="img/refill/refill-theme-mallorca_color.jpg" width=780 height=270>

<img src="img/refill/refill-theme-mallorca_2color.jpg" width=780 height=270>

#### black

_Black is the default Refill theme color._

Current **MAJOR** versioned release:

* `https://mapzen.com/carto/refill-style/7/themes/black.zip`
* `https://mapzen.com/carto/refill-style-more-labels/7/themes/black.zip`
* `https://mapzen.com/carto/refill-style-no-labels/7/themes/black.zip`

#### blue

Current **MAJOR** versioned release:

* `https://mapzen.com/carto/refill-style/7/themes/blue.zip`
* `https://mapzen.com/carto/refill-style-more-labels/7/themes/blue.zip`
* `https://mapzen.com/carto/refill-style-no-labels/7/themes/blue.zip`

#### blue-gray

Current **MAJOR** versioned release:

* `https://mapzen.com/carto/refill-style/7/themes/blue-gray.zip`
* `https://mapzen.com/carto/refill-style-more-labels/7/themes/blue-gray.zip`
* `https://mapzen.com/carto/refill-style-no-labels/7/themes/blue-gray.zip`


#### brown-orange

Current **MAJOR** versioned release:

* `https://mapzen.com/carto/refill-style/7/themes/brown-orange.zip`
* `https://mapzen.com/carto/refill-style-more-labels/7/themes/brown-orange.zip`
* `https://mapzen.com/carto/refill-style-no-labels/7/themes/brown-orange.zip`


#### gray

Current **MAJOR** versioned release:

* `https://mapzen.com/carto/refill-style/7/themes/gray.zip`
* `https://mapzen.com/carto/refill-style-more-labels/7/themes/gray.zip`
* `https://mapzen.com/carto/refill-style-no-labels/7/themes/gray.zip`


#### high-contrast

Current **MAJOR** versioned release:

* `https://mapzen.com/carto/refill-style/7/themes/high-contrast.zip`
* `https://mapzen.com/carto/refill-style-more-labels/7/themes/high-contrast.zip`
* `https://mapzen.com/carto/refill-style-no-labels/7/themes/high-contrast.zip`


#### pink

Current **MAJOR** versioned release:

* `https://mapzen.com/carto/refill-style/7/themes/pink.zip`
* `https://mapzen.com/carto/refill-style-more-labels/7/themes/pink.zip`
* `https://mapzen.com/carto/refill-style-no-labels/7/themes/pink.zip`


#### pink-yellow

Current **MAJOR** versioned release:

* `https://mapzen.com/carto/refill-style/7/themes/pink-yellow.zip`
* `https://mapzen.com/carto/refill-style-more-labels/7/themes/pink-yellow.zip`
* `https://mapzen.com/carto/refill-style-no-labels/7/themes/pink-yellow.zip`


#### sepia

Current **MAJOR** versioned release:

* `https://mapzen.com/carto/refill-style/7/themes/sepia.zip`
* `https://mapzen.com/carto/refill-style-more-labels/7/themes/sepia.zip`
* `https://mapzen.com/carto/refill-style-no-labels/7/themes/sepia.zip`
