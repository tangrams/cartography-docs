# API reference

Mapzen basemaps offer several global properties to customize and extend the map.

Not every basemap supports the full set of resources and the default styling of these assets is customized per Mapzen map style. See [Styles](styles.md) for what's supported.

As the basemaps are still in active development we recommend pegging an import to a specific major version, eg: `6`. See the [versioning](versioning.md) doc for more details.

## Mapzen API keys

Mapzen basemaps require setting a Mapzen API key to access related Mapzen vector tile and terrain tile services.

[Sign up](https://mapzen.com/documentation/overview/#developer-accounts-and-api-keys) for a Mapzen API key here.

### sdk_api_key

* `sdk_mapzen_api_key`: defaults to `''` (an empty string)

Example **Tangram YAML** usage:

```
import: https://mapzen.com/carto/refill-style/6/refill-style.yaml

global:
    sdk_mapzen_api_key: mapzen-xxxxxx
```

Example **Tangram JS** usage:

```
var layer = Tangram.leafletLayer({
    scene: {
      import: 'https://mapzen.com/carto/refill-style/6/refill-style.yaml',
      global: { sdk_mapzen_api_key: 'mapzen-xxxxxx' }
    });
```

Example **Mapzen.js** usage (all services):

```
L.Mapzen.apiKey = 'mapzen-xxxxxx';

var map = L.Mapzen.map('map', {
  center: [40.8041, -124.1506],
  zoom: 15,
  maxZoom: 20,
  tangramOptions: {
    scene: {
      import: L.Mapzen.BasemapStyles.Refill,
    }
  }
});
```

Example **Mapzen.js** usage (just Tangram):

```
var map = L.Mapzen.map('map', {
  center: [40.8041, -124.1506],
  zoom: 15,
  maxZoom: 20,
  tangramOptions: {
    scene: {
      import: L.Mapzen.BasemapStyles.Refill,
      global: {
        sdk_mapzen_api_key: 'mapzen-xxxxxx'
      }
    }
  }
});
```

Example **Tangram ES** usage:

```
map->loadScene(
    "https://mapzen.com/carto/refill-style/6/refill-style.yaml",
    false,
    { "global.sdk_mapzen_api_key", "mapzen-xxxxxx" }
);
```

## Language

Feature labels default to the local language used in that place but can be modified to show a specific language using [ISO 639-1](https://en.wikipedia.org/wiki/List_of_ISO_639-1_codes) two-letter language code and optional country code, for example `en` for English and less commonly `en_GB` for British English.

If you ask for a language that isn't present in the data, it will automatically fallback to the default (local) language.

### ux_language

* `ux_language`: defaults to `false`

Example **Tangram YAML** usage:

```
import: https://mapzen.com/carto/refill-style/6/refill-style.yaml

global:
    ux_language: fr
```

Example **Mapzen.js** usage:

```
var map = L.Mapzen.map('map', {
  center: [40.8041, -124.1506],
  zoom: 15,
  maxZoom: 20,
  tangramOptions: {
    scene: {
      import: L.Mapzen.BasemapStyles.Refill,
      global: {
        ux_language: 'en'
      }
    }
  }
});
```

### ux_language_fallback

Because language coverage is spotty in the data, it's sometimes useful to pair with a **fallback** language.

For instance, if someone reads French but not Japanese they would prefer to see French labels in Tokyo. But since there aren't many French names available it's better to fallback to English names since they would be in the same alphabet, before falling all the way back to default (local) Japanese names.

* `ux_language_fallback`: defaults to `false`

Example **Tangram YAML** usage:

```
import: https://mapzen.com/carto/refill-style/6/refill-style.yaml

global:
    ux_language: fr
    ux_language_fallback: en
```

### Language codes

Common language codes values include:

- `ar` Arabic
- `zh` Chinese, traditional or simplified
- `en` English
- `fr` French
- `ru` Russian
- `es` Spanish
- `bn` Bengali
- `de` German
- `gr` Greek
- `hi` Hindi
- `id` Indonesian
- `it` Italian
- `ja` Japanese
- `ko` Korean
- `pt` Portugese
- `tr` Turkish
- `vi` Vietnamese

## Labels

Icons and text add dimensionality and insight to a map and can be altered for your use case.

### Road shields

Road shield artwork can be disabled. This can be useful when showing transit overlay and in data visualization use cases.

* `sdk_road_shields`: default `true`

Example **Tangram YAML** usage:

```
import: https://mapzen.com/carto/refill-style/6/refill-style.yaml

global:
    sdk_road_shields: false
```

## Basemap styling

Roads are red, parks are green, water is blue, and buildings extrude.

### Building extrusion

Are the 3d buildings distracting? Turn them off.

* `sdk_building_extrude`: default `true` (except for Zinc which is default `false)

Example **Tangram YAML** usage:

```
import: https://mapzen.com/carto/refill-style/6/refill-style.yaml

global:
    sdk_building_extrude: false
```

## Data visualization

To facilitate map customization and data visualizations several recommended sort orders are provided. The order properties abstract the values which work with specific versions of Mapzen vector tiles (see [feature ordering](https://mapzen.com/documentation/vector-tiles/layers/#feature-ordering) docs).

Example **Tangram YAML** usage:

```
import: https://mapzen.com/carto/refill-style/6/refill-style.yaml

_layername:
    draw:
        line:
            order: global.sdk_order_over_everything_but_text_0
            width: 1px
            color: red
```

### Overlay

Your classic overlay: Over all line and polygon features, but under map labels (icons and text), and under UI elements (like route line and search result pins).

* `sdk_order_over_everything_but_text_0`: default
* `sdk_order_over_everything_but_text_1`: one above default
* `sdk_order_over_everything_but_text_2`: two above default
* `sdk_order_over_everything_but_text_3`: three above default
* `sdk_order_over_everything_but_text_4`: four above default
* `sdk_order_over_everything_but_text_5`: five above default
* `sdk_order_over_everything_but_text_6`: six above default
* `sdk_order_over_everything_but_text_7`: seven above default
* `sdk_order_over_everything_but_text_8`: eight above default
* `sdk_order_over_everything_but_text_9`: nine above default

### Basic underlay

Under roads. Above borders, water, landuse, and earth.

* `sdk_order_under_roads_0`: default
* `sdk_order_under_roads_1`: one above default
* `sdk_order_under_roads_2`: twp above default
* `sdk_order_under_roads_3`: three above default
* `sdk_order_under_roads_4`: four above default
* `sdk_order_under_roads_5`: five above default
* `sdk_order_under_roads_6`: six above default
* `sdk_order_under_roads_7`: seven above default
* `sdk_order_under_roads_8`: eight above default
* `sdk_order_under_roads_9`: nine above default

### Under water

Above earth and most landuse.

* `sdk_order_under_water_0`: default
* `sdk_order_under_water_1`: one above default
* `sdk_order_under_water_2`: two above default
* `sdk_order_under_water_3`: three above default
* `sdk_order_under_water_4`: four above default
* `sdk_order_under_water_5`: five above default
* `sdk_order_under_water_6`: six above default
* `sdk_order_under_water_7`: seven above default
* `sdk_order_under_water_8`: eight above default
* `sdk_order_under_water_9`: nine above default

### Under everything

Tip: disable earth layer.

* `sdk_order_under_everything_0`: default
* `sdk_order_under_everything_1`: one above default
* `sdk_order_under_everything_2`: two above default
* `sdk_order_under_everything_3`: three above default
* `sdk_order_under_everything_4`: four above default
* `sdk_order_under_everything_5`: five above default
* `sdk_order_under_everything_6`: six above default
* `sdk_order_under_everything_7`: seven above default
* `sdk_order_under_everything_8`: eight above default
* `sdk_order_under_everything_9`: nine above default

## Transit overlay

All basemap styles support transit overlays.

* `sdk_transit_overlay`: default `false`

Example **Tangram YAML** usage:

```
import: https://mapzen.com/carto/refill-style/6/refill-style.yaml

global:
    sdk_transit_overlay: true
```

## Bicycle overlay

Some basemap styles support bicycle overlays (only Walkabout). When enabling the bike map we recommend also disabling the path overlay.

* `sdk_bike_overlay`: default `false`

Example **Tangram YAML** usage:

```
import: https://mapzen.com/carto/walkabout-style/4/walkabout-style.yaml

global:
    sdk_bike_overlay: true
    sdk_path_overlay: false
```

**Legend** Walkabout bike map categories and icon treatments

<img alt='Walkabout Bike Map Legend' src='./img/walkabout-style-bike-map-legend-combo.png' width='300' height='420' align='right'>


## Path overlay

Some basemap styles support path overlays (only Walkabout).

* `sdk_path_overlay`: default `true`

Example **Tangram YAML** usage:

```
import: https://mapzen.com/carto/walkabout-style/4/walkabout-style.yaml

global:
    sdk_path_overlay: false
```

## Default draw styles

Custom **draw styles** for icons, point, shield, line, and polygon overlays on the map. These set the feature order and blend order to be a standard overlay. For icons, point, and shield styles a default sprite is also set.

Special `mz_*` **data sources** are available to automatically render content using the associated draw styles for point, shield, line, and polygon draw styles. To render features in one of these draw styles, create the specified `mz_*` data source.

Example **Tangram YAML** examples for `mz_*` source names:

```
import: https://mapzen.com/carto/refill-style/6/refill-style.yaml

sources:
    mz_default_polygon:
        type: GeoJSON
        url:  https://example.com/filename.geojson
```

### Icons

* **draw style:** `icons`
* **sprite:** multiple sprites supported in the `pois` texture, see [icon library](icons.md)

Example **Tangram YAML** usage:

```
import: https://mapzen.com/carto/refill-style/6/refill-style.yaml

sources:
    _my_source:
        type: GeoJSON
        url:  https://example.com/filename.geojson

layers:
    _my_layer:
        data: { source: _my_source }
        draw:
            icons:
                size: [[13, 18px], [16, 18px], [18, 22px]]
                sprite: zoo
```

### Points

* **draw style:** `sdk-point-overlay`
* **sprite:** `ux-search-active`
* **data source:** `mz_default_point`

### Shields

* **draw style:** `sdk-shield-overlay`
* **sprite:** `sdk_shield_1char`, `sdk_shield_2char`, `sdk_shield_3char`, `sdk_shield_4char`, `sdk_shield_5char`
* **data source:** `mz_default_shield`

### Lines

* **draw style:** `sdk-line-overlay`
* **data source:** `mz_default_line`

### Polygons

* **draw style:** `sdk-polygon-overlay`
* **data source:** `mz_default_polygon`

## User experience

Several special data sources, draw styles, and sprites (icons) are provided for building and customizing mapping applications. These set the feature order and blend order to be above all other map elements.

If you add a any of the following named data sources to the scene file (or update features into the named data source) the draw style will activate automatically.

### Current location

* **draw style:** `ux-location-gem-overlay`
* **sprite:** `ux-current-location`
* **data source:** `mz_current_location`

### Dropped pin

* **draw style:** `ux-icons-overlay`
* **sprite:** `ux-search-active`
* **data source:** `mz_dropped_pin`

### Search results

* **draw style:** `ux-icons-overlay`
* **sprite:** `ux-search-active`
* **data source:** `mz_search_result`

When a search feature is marked `state: inactive`, the following resources is used:

* **sprite:** `ux-search-inactive`

### Routing

#### Route line

* **draw style:** `ux-route-line-overlay`
* **data source:** `mz_route_line`

#### Progress along the route line

* **draw style:** `ux-location-gem-overlay`
* **sprite:** `ux-route-arrow`
* **data source:** `mz_route_location`

#### Starting location icon

* **draw style:** `ux-icons-overlay`
* **sprite:** `ux-route-start`
* **data source:** `mz_route_start`

#### Destination location icon

* **draw style:** `ux-icons-overlay`
* **sprite:** `ux-route-stop`
* **data source:** `mz_route_destination`

#### Transit route line

Each transit route segment could be a different "line" each with it's own `color` data driven styling. But some transit lines don't define a color, in those cases default to blue.

* **data source feature property:** `color`
* **draw style:** `ux-transit-line-overlay`
* **data source:** `mz_route_line_transit`

#### Transit stop

For major transit stops related to onboarding, offboarding, and transfers. If pass-thru stops are provided in the data source they will also be rendered (but are not in the general Mapzen Turn-by-Turn response).

* **draw style:** `ux-icons-overlay`
* **sprite:** `ux-transit-stop`
* **data source:** `mz_route_transit_stop`

#### Dashed route line

Used to show walking segments of multi-modal routes.

* **draw style:** `ux-route-line-dash-overlay`
* **data source:** `mz_dash_line`
