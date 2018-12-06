# Shield Library - USA

Mapzen basemap styles include custom shields to display road network on a map. These can be used interchangeably between the different basemaps or in a custom [Tangram map](https://mapzen.com/documentation/tangram) of your own.

The library has expanded to a several hundred icons. Most, but not all icons, are available in 4 or more styles.

There are no rights restrictions on the icons. The examples below are for Tangram but you are free to use the icons in your favorite mapping library or application. The original Illustrator [vector artwork](https://github.com/tangrams/icons) is also available.

## Using built-in sprites

Shields can be added to a Tangram map using the [sprites property](https://mapzen.com/documentation/tangram/draw/#sprite) of the `mapzen_icon_library` draw style.

### By shield name

Import the Refill basemap style (which includes the Mapzen icon library) and draw user-provided points on the map using the library's **zoo** icon.

```
import:
    - https://mapzen.com/carto/refill-style/10/refill-style.zip

sources:
    my-source:
        type: GeoJSON
        url:  https://example.com/filename.geojson

layers:
    my-layer:
        data:
            source: my-source
        draw:
            mapzen_icon_library:
                sprite: zoo
```

### Data-driven styling

Data-driven styling is supported when your data includes a `network` property with values matched to the shield names in the table. Data is evaluated on a per-feature basis so you'll end up with a variety of icons shown on the map.

```
import:
    - https://mapzen.com/carto/refill-style/10/refill-style.zip

sources:
    my-source:
        type: GeoJSON
        url:  https://example.com/filename.geojson

layers:
    my-layer:
        data:
            source: my-source
        draw:
            mapzen_icon_library: {}
```

## Using Mapzen shields independently

### Tangram

You can use the shields in the Mapzen icon library independent of Mapzen basemap styles by importing just the shield bundle into a Tangram scene.

* `https://mapzen.com/carto/bubble-wrap-style/10/themes/bubble-wrap-icons.zip`
* `https://mapzen.com/carto/cinnabar-style/10/themes/cinnabar-icons.zip`
* `https://mapzen.com/carto/refill-style/12/themes/refill-icons.zip`
* `https://mapzen.com/carto/tron-style/6/themes/tron-icons.zip`
* `https://mapzen.com/carto/walkabout-style/8/themes/walkabout-icons.zip`
* `https://mapzen.com/carto/sdk-default-style/1/themes/sdk-default-icons.zip`

For example:

```
import:
    - https://mapzen.com/carto/refill-style/10/themes/refill-icons.zip

sources:
    my-source:
        type: GeoJSON
        url:  https://example.com/filename.geojson

layers:
    my-layer:
        data:
            source: my-source
        draw:
            mapzen_icon_library:
                sprite: zoo
```

### Sprites

The Mapzen Icon Library is available for use in your favorite mapping or graphics software as individual sprite images.

Currently only only `png` format at `2x` resolution is supported.

* `https://mapzen.com/carto/bubble-wrap-style/10/icons/{resolution}/{sprite}.{format}`
* `https://mapzen.com/carto/cinnabar-style/10/icons/{resolution}/{sprite}.{format}`
* `https://mapzen.com/carto/refill-style/12/icons/{resolution}/{sprite}.{format}`
* `https://mapzen.com/carto/tron-style/6/icons/{resolution}/{sprite}.{format}`
* `https://mapzen.com/carto/walkabout-style/8/icons/{resolution}/{sprite}.{format}`
* `https://mapzen.com/carto/sdk-default-style/1/icons/{resolution}/{sprite}.{format}`

**For example:**

Load the `US:US` sprite in the **Bubble Wrap** style at `2x` in `png` format:

```
https://mapzen.com/carto/bubble-wrap-style/10/shields-usa/2x/us/us.png
```

## Customize shield colors

You can customize the shield colors by changing the global color of colorized-icons in styles. Assign the color in the global u_tint. If you would like to color the badge fill area, assign the color in the draw layer. See below:

```
import:
    - https://mapzen.com/carto/refill-style/10/themes/refill-icons.zip

sources:
    my-source:
        type: GeoJSON
        url:  https://example.com/filename.geojson

styles:
    colorized-icons:
        shaders:
            uniforms:
                # color the icon here
                u_tint: [0.925,0.090,0.094]

layers:
    my-layer:
        data:
            source: my-source
        draw:
            mapzen_icon_library:
                # color the badge fill area here
                color: [0.724,1.000,0.893]
                sprite: zoo
```

### Mix and match icon styles

You could even use the Bubble Wrap shields on Refill!

```
import:
    - https://mapzen.com/carto/refill-style/10/refill-style.zip
    - https://mapzen.com/carto/bubble-wrap-style/12/themes/bubble-wrap-road-shields-usa.zip
```

## Sprites

Sprite names generally match the `network` values from the [Mapzen vector tiles](https://mapzen.com/documentation/vector-tiles/layers/#roads-transportation) roads transportation layer.

Size variants are provided for 1, 2, 3, 4, and 5 character width shield text. The 2-character variant is depicted below.

sprite | Bubble Wrap | Walkabout | Refill | Cinnabar
:----- | :---------: | :-------: | :----: | :------:
`US:AK` |  ![US:AK](img/sprite/bubble-wrap-style/shields-usa/2x/US:AK-2char.png) | ![US:AK](img/sprite/walkabout-style/shields-usa/2x/US:AK-2char.png) | ![US:AK](img/sprite/refill-style/shields-usa/2x/US:AK-2char.png) | ![US:AK](img/sprite/refill-style/shields-usa/2x/US:AK-2char.png)
`US:AL` |  ![US:AL](img/sprite/bubble-wrap-style/shields-usa/2x/US:AL-2char.png) | ![US:AL](img/sprite/walkabout-style/shields-usa/2x/US:AL-2char.png) | ![US:AL](img/sprite/refill-style/shields-usa/2x/US:AL-2char.png) | ![US:AL](img/sprite/refill-style/shields-usa/2x/US:AL-2char.png)
`US:AR` |  ![US:AR](img/sprite/bubble-wrap-style/shields-usa/2x/US:AR-2char.png) | ![US:AR](img/sprite/walkabout-style/shields-usa/2x/US:AR-2char.png) | ![US:AR](img/sprite/refill-style/shields-usa/2x/US:AR-2char.png) | ![US:AR](img/sprite/refill-style/shields-usa/2x/US:AR-2char.png)
`US:AZ` |  ![US:AZ](img/sprite/bubble-wrap-style/shields-usa/2x/US:AZ-2char.png) | ![US:AZ](img/sprite/walkabout-style/shields-usa/2x/US:AZ-2char.png) | ![US:AZ](img/sprite/refill-style/shields-usa/2x/US:AZ-2char.png) | ![US:AZ](img/sprite/refill-style/shields-usa/2x/US:AZ-2char.png)
`US:BIA` |  ![US:BIA](img/sprite/bubble-wrap-style/shields-usa/2x/US:BIA-2char.png) | ![US:BIA](img/sprite/walkabout-style/shields-usa/2x/US:BIA-2char.png) | ![US:BIA](img/sprite/refill-style/shields-usa/2x/US:BIA-2char.png) | ![US:BIA](img/sprite/refill-style/shields-usa/2x/US:BIA-2char.png)
`US:BLM` |  ![US:BLM](img/sprite/bubble-wrap-style/shields-usa/2x/US:BLM-2char.png) | ![US:BLM](img/sprite/walkabout-style/shields-usa/2x/US:BLM-2char.png) | ![US:BLM](img/sprite/refill-style/shields-usa/2x/US:BLM-2char.png) | ![US:BLM](img/sprite/refill-style/shields-usa/2x/US:BLM-2char.png)
`US:CA` |  ![US:CA](img/sprite/bubble-wrap-style/shields-usa/2x/US:CA-2char.png) | ![US:CA](img/sprite/walkabout-style/shields-usa/2x/US:CA-2char.png) | ![US:CA](img/sprite/refill-style/shields-usa/2x/US:CA-2char.png) | ![US:CA](img/sprite/refill-style/shields-usa/2x/US:CA-2char.png)
`US:CO` |  ![US:CO](img/sprite/bubble-wrap-style/shields-usa/2x/US:CO-2char.png) | ![US:CO](img/sprite/walkabout-style/shields-usa/2x/US:CO-2char.png) | ![US:CO](img/sprite/refill-style/shields-usa/2x/US:CO-2char.png) | ![US:CO](img/sprite/refill-style/shields-usa/2x/US:CO-2char.png)
`US:CT` |  ![US:CT](img/sprite/bubble-wrap-style/shields-usa/2x/US:CT-2char.png) | ![US:CT](img/sprite/walkabout-style/shields-usa/2x/US:CT-2char.png) | ![US:CT](img/sprite/refill-style/shields-usa/2x/US:CT-2char.png) | ![US:CT](img/sprite/refill-style/shields-usa/2x/US:CT-2char.png)
`US:DC` |  ![US:DC](img/sprite/bubble-wrap-style/shields-usa/2x/US:DC-2char.png) | ![US:DC](img/sprite/walkabout-style/shields-usa/2x/US:DC-2char.png) | ![US:DC](img/sprite/refill-style/shields-usa/2x/US:DC-2char.png) | ![US:DC](img/sprite/refill-style/shields-usa/2x/US:DC-2char.png)
`US:DE` |  ![US:DE](img/sprite/bubble-wrap-style/shields-usa/2x/US:DE-2char.png) | ![US:DE](img/sprite/walkabout-style/shields-usa/2x/US:DE-2char.png) | ![US:DE](img/sprite/refill-style/shields-usa/2x/US:DE-2char.png) | ![US:DE](img/sprite/refill-style/shields-usa/2x/US:DE-2char.png)
`US:FL` |  ![US:FL](img/sprite/bubble-wrap-style/shields-usa/2x/US:FL-2char.png) | ![US:FL](img/sprite/walkabout-style/shields-usa/2x/US:FL-2char.png) | ![US:FL](img/sprite/refill-style/shields-usa/2x/US:FL-2char.png) | ![US:FL](img/sprite/refill-style/shields-usa/2x/US:FL-2char.png)
`US:FSH` |  ![US:FSH](img/sprite/bubble-wrap-style/shields-usa/2x/US:FSH-2char.png) | ![US:FSH](img/sprite/walkabout-style/shields-usa/2x/US:FSH-2char.png) | ![US:FSH](img/sprite/refill-style/shields-usa/2x/US:FSH-2char.png) | ![US:FSH](img/sprite/refill-style/shields-usa/2x/US:FSH-2char.png)
`US:FSR` |  ![US:FSR](img/sprite/bubble-wrap-style/shields-usa/2x/US:FSR-2char.png) | ![US:FSR](img/sprite/walkabout-style/shields-usa/2x/US:FSR-2char.png) | ![US:FSR](img/sprite/refill-style/shields-usa/2x/US:FSR-2char.png) | ![US:FSR](img/sprite/refill-style/shields-usa/2x/US:FSR-2char.png)
`US:GA` |  ![US:GA](img/sprite/bubble-wrap-style/shields-usa/2x/US:GA-2char.png) | ![US:GA](img/sprite/walkabout-style/shields-usa/2x/US:GA-2char.png) | ![US:GA](img/sprite/refill-style/shields-usa/2x/US:GA-2char.png) | ![US:GA](img/sprite/refill-style/shields-usa/2x/US:GA-2char.png)
`US:HI` |  ![US:HI](img/sprite/bubble-wrap-style/shields-usa/2x/US:HI-2char.png) | ![US:HI](img/sprite/walkabout-style/shields-usa/2x/US:HI-2char.png) | ![US:HI](img/sprite/refill-style/shields-usa/2x/US:HI-2char.png) | ![US:HI](img/sprite/refill-style/shields-usa/2x/US:HI-2char.png)
`US:I` |  ![US:I](img/sprite/bubble-wrap-style/shields-usa/2x/US:I-2char.png) | ![US:I](img/sprite/walkabout-style/shields-usa/2x/US:I-2char.png) | ![US:I](img/sprite/refill-style/shields-usa/2x/US:I-2char.png) | ![US:I](img/sprite/refill-style/shields-usa/2x/US:I-2char.png)
`US:I:Alternate` |  ![US:I:Alternate](img/sprite/bubble-wrap-style/shields-usa/2x/US:I:Alternate-2char.png) | ![US:I:Alternate](img/sprite/walkabout-style/shields-usa/2x/US:I:Alternate-2char.png) | ![US:I:Alternate](img/sprite/refill-style/shields-usa/2x/US:I:Alternate-2char.png) | ![US:I:Alternate](img/sprite/refill-style/shields-usa/2x/US:I:Alternate-2char.png)
`US:I:Business` |  ![US:I:Business](img/sprite/bubble-wrap-style/shields-usa/2x/US:I:Business-2char.png) | ![US:I:Business](img/sprite/walkabout-style/shields-usa/2x/US:I:Business-2char.png) | ![US:I:Business](img/sprite/refill-style/shields-usa/2x/US:I:Business-2char.png) | ![US:I:Business](img/sprite/refill-style/shields-usa/2x/US:I:Business-2char.png)
`US:I:Truck` |  ![US:I:Truck](img/sprite/bubble-wrap-style/shields-usa/2x/US:I:Truck-2char.png) | ![US:I:Truck](img/sprite/walkabout-style/shields-usa/2x/US:I:Truck-2char.png) | ![US:I:Truck](img/sprite/refill-style/shields-usa/2x/US:I:Truck-2char.png) | ![US:I:Truck](img/sprite/refill-style/shields-usa/2x/US:I:Truck-2char.png)
`US:IA` |  ![US:IA](img/sprite/bubble-wrap-style/shields-usa/2x/US:IA-2char.png) | ![US:IA](img/sprite/walkabout-style/shields-usa/2x/US:IA-2char.png) | ![US:IA](img/sprite/refill-style/shields-usa/2x/US:IA-2char.png) | ![US:IA](img/sprite/refill-style/shields-usa/2x/US:IA-2char.png)
`US:ID` |  ![US:ID](img/sprite/bubble-wrap-style/shields-usa/2x/US:ID-2char.png) | ![US:ID](img/sprite/walkabout-style/shields-usa/2x/US:ID-2char.png) | ![US:ID](img/sprite/refill-style/shields-usa/2x/US:ID-2char.png) | ![US:ID](img/sprite/refill-style/shields-usa/2x/US:ID-2char.png)
`US:IL` |  ![US:IL](img/sprite/bubble-wrap-style/shields-usa/2x/US:IL-2char.png) | ![US:IL](img/sprite/walkabout-style/shields-usa/2x/US:IL-2char.png) | ![US:IL](img/sprite/refill-style/shields-usa/2x/US:IL-2char.png) | ![US:IL](img/sprite/refill-style/shields-usa/2x/US:IL-2char.png)
`US:IN` |  ![US:IN](img/sprite/bubble-wrap-style/shields-usa/2x/US:IN-2char.png) | ![US:IN](img/sprite/walkabout-style/shields-usa/2x/US:IN-2char.png) | ![US:IN](img/sprite/refill-style/shields-usa/2x/US:IN-2char.png) | ![US:IN](img/sprite/refill-style/shields-usa/2x/US:IN-2char.png)
`US:KS` |  ![US:KS](img/sprite/bubble-wrap-style/shields-usa/2x/US:KS-2char.png) | ![US:KS](img/sprite/walkabout-style/shields-usa/2x/US:KS-2char.png) | ![US:KS](img/sprite/refill-style/shields-usa/2x/US:KS-2char.png) | ![US:KS](img/sprite/refill-style/shields-usa/2x/US:KS-2char.png)
`US:KY` |  ![US:KY](img/sprite/bubble-wrap-style/shields-usa/2x/US:KY-2char.png) | ![US:KY](img/sprite/walkabout-style/shields-usa/2x/US:KY-2char.png) | ![US:KY](img/sprite/refill-style/shields-usa/2x/US:KY-2char.png) | ![US:KY](img/sprite/refill-style/shields-usa/2x/US:KY-2char.png)
`US:LA` |  ![US:LA](img/sprite/bubble-wrap-style/shields-usa/2x/US:LA-2char.png) | ![US:LA](img/sprite/walkabout-style/shields-usa/2x/US:LA-2char.png) | ![US:LA](img/sprite/refill-style/shields-usa/2x/US:LA-2char.png) | ![US:LA](img/sprite/refill-style/shields-usa/2x/US:LA-2char.png)
`US:MA` |  ![US:MA](img/sprite/bubble-wrap-style/shields-usa/2x/US:MA-2char.png) | ![US:MA](img/sprite/walkabout-style/shields-usa/2x/US:MA-2char.png) | ![US:MA](img/sprite/refill-style/shields-usa/2x/US:MA-2char.png) | ![US:MA](img/sprite/refill-style/shields-usa/2x/US:MA-2char.png)
`US:MD` |  ![US:MD](img/sprite/bubble-wrap-style/shields-usa/2x/US:MD-2char.png) | ![US:MD](img/sprite/walkabout-style/shields-usa/2x/US:MD-2char.png) | ![US:MD](img/sprite/refill-style/shields-usa/2x/US:MD-2char.png) | ![US:MD](img/sprite/refill-style/shields-usa/2x/US:MD-2char.png)
`US:ME` |  ![US:ME](img/sprite/bubble-wrap-style/shields-usa/2x/US:ME-2char.png) | ![US:ME](img/sprite/walkabout-style/shields-usa/2x/US:ME-2char.png) | ![US:ME](img/sprite/refill-style/shields-usa/2x/US:ME-2char.png) | ![US:ME](img/sprite/refill-style/shields-usa/2x/US:ME-2char.png)
`US:MI` |  ![US:MI](img/sprite/bubble-wrap-style/shields-usa/2x/US:MI-2char.png) | ![US:MI](img/sprite/walkabout-style/shields-usa/2x/US:MI-2char.png) | ![US:MI](img/sprite/refill-style/shields-usa/2x/US:MI-2char.png) | ![US:MI](img/sprite/refill-style/shields-usa/2x/US:MI-2char.png)
`US:MN` |  ![US:MN](img/sprite/bubble-wrap-style/shields-usa/2x/US:MN-2char.png) | ![US:MN](img/sprite/walkabout-style/shields-usa/2x/US:MN-2char.png) | ![US:MN](img/sprite/refill-style/shields-usa/2x/US:MN-2char.png) | ![US:MN](img/sprite/refill-style/shields-usa/2x/US:MN-2char.png)
`US:MO` |  ![US:MO](img/sprite/bubble-wrap-style/shields-usa/2x/US:MO-2char.png) | ![US:MO](img/sprite/walkabout-style/shields-usa/2x/US:MO-2char.png) | ![US:MO](img/sprite/refill-style/shields-usa/2x/US:MO-2char.png) | ![US:MO](img/sprite/refill-style/shields-usa/2x/US:MO-2char.png)
`US:MS` |  ![US:MS](img/sprite/bubble-wrap-style/shields-usa/2x/US:MS-2char.png) | ![US:MS](img/sprite/walkabout-style/shields-usa/2x/US:MS-2char.png) | ![US:MS](img/sprite/refill-style/shields-usa/2x/US:MS-2char.png) | ![US:MS](img/sprite/refill-style/shields-usa/2x/US:MS-2char.png)
`US:MT` |  ![US:MT](img/sprite/bubble-wrap-style/shields-usa/2x/US:MT-2char.png) | ![US:MT](img/sprite/walkabout-style/shields-usa/2x/US:MT-2char.png) | ![US:MT](img/sprite/refill-style/shields-usa/2x/US:MT-2char.png) | ![US:MT](img/sprite/refill-style/shields-usa/2x/US:MT-2char.png)
`US:NC` |  ![US:NC](img/sprite/bubble-wrap-style/shields-usa/2x/US:NC-2char.png) | ![US:NC](img/sprite/walkabout-style/shields-usa/2x/US:NC-2char.png) | ![US:NC](img/sprite/refill-style/shields-usa/2x/US:NC-2char.png) | ![US:NC](img/sprite/refill-style/shields-usa/2x/US:NC-2char.png)
`US:ND` |  ![US:ND](img/sprite/bubble-wrap-style/shields-usa/2x/US:ND-2char.png) | ![US:ND](img/sprite/walkabout-style/shields-usa/2x/US:ND-2char.png) | ![US:ND](img/sprite/refill-style/shields-usa/2x/US:ND-2char.png) | ![US:ND](img/sprite/refill-style/shields-usa/2x/US:ND-2char.png)
`US:NE` |  ![US:NE](img/sprite/bubble-wrap-style/shields-usa/2x/US:NE-2char.png) | ![US:NE](img/sprite/walkabout-style/shields-usa/2x/US:NE-2char.png) | ![US:NE](img/sprite/refill-style/shields-usa/2x/US:NE-2char.png) | ![US:NE](img/sprite/refill-style/shields-usa/2x/US:NE-2char.png)
`US:NH` |  ![US:NH](img/sprite/bubble-wrap-style/shields-usa/2x/US:NH-2char.png) | ![US:NH](img/sprite/walkabout-style/shields-usa/2x/US:NH-2char.png) | ![US:NH](img/sprite/refill-style/shields-usa/2x/US:NH-2char.png) | ![US:NH](img/sprite/refill-style/shields-usa/2x/US:NH-2char.png)
`US:NJ` |  ![US:NJ](img/sprite/bubble-wrap-style/shields-usa/2x/US:NJ-2char.png) | ![US:NJ](img/sprite/walkabout-style/shields-usa/2x/US:NJ-2char.png) | ![US:NJ](img/sprite/refill-style/shields-usa/2x/US:NJ-2char.png) | ![US:NJ](img/sprite/refill-style/shields-usa/2x/US:NJ-2char.png)
`US:NM` |  ![US:NM](img/sprite/bubble-wrap-style/shields-usa/2x/US:NM-2char.png) | ![US:NM](img/sprite/walkabout-style/shields-usa/2x/US:NM-2char.png) | ![US:NM](img/sprite/refill-style/shields-usa/2x/US:NM-2char.png) | ![US:NM](img/sprite/refill-style/shields-usa/2x/US:NM-2char.png)
`US:NV` |  ![US:NV](img/sprite/bubble-wrap-style/shields-usa/2x/US:NV-2char.png) | ![US:NV](img/sprite/walkabout-style/shields-usa/2x/US:NV-2char.png) | ![US:NV](img/sprite/refill-style/shields-usa/2x/US:NV-2char.png) | ![US:NV](img/sprite/refill-style/shields-usa/2x/US:NV-2char.png)
`US:NY` |  ![US:NY](img/sprite/bubble-wrap-style/shields-usa/2x/US:NY-2char.png) | ![US:NY](img/sprite/walkabout-style/shields-usa/2x/US:NY-2char.png) | ![US:NY](img/sprite/refill-style/shields-usa/2x/US:NY-2char.png) | ![US:NY](img/sprite/refill-style/shields-usa/2x/US:NY-2char.png)
`US:OH` |  ![US:OH](img/sprite/bubble-wrap-style/shields-usa/2x/US:OH-2char.png) | ![US:OH](img/sprite/walkabout-style/shields-usa/2x/US:OH-2char.png) | ![US:OH](img/sprite/refill-style/shields-usa/2x/US:OH-2char.png) | ![US:OH](img/sprite/refill-style/shields-usa/2x/US:OH-2char.png)
`US:OK` |  ![US:OK](img/sprite/bubble-wrap-style/shields-usa/2x/US:OK-2char.png) | ![US:OK](img/sprite/walkabout-style/shields-usa/2x/US:OK-2char.png) | ![US:OK](img/sprite/refill-style/shields-usa/2x/US:OK-2char.png) | ![US:OK](img/sprite/refill-style/shields-usa/2x/US:OK-2char.png)
`US:OR` |  ![US:OR](img/sprite/bubble-wrap-style/shields-usa/2x/US:OR-2char.png) | ![US:OR](img/sprite/walkabout-style/shields-usa/2x/US:OR-2char.png) | ![US:OR](img/sprite/refill-style/shields-usa/2x/US:OR-2char.png) | ![US:OR](img/sprite/refill-style/shields-usa/2x/US:OR-2char.png)
`US:PA` |  ![US:PA](img/sprite/bubble-wrap-style/shields-usa/2x/US:PA-2char.png) | ![US:PA](img/sprite/walkabout-style/shields-usa/2x/US:PA-2char.png) | ![US:PA](img/sprite/refill-style/shields-usa/2x/US:PA-2char.png) | ![US:PA](img/sprite/refill-style/shields-usa/2x/US:PA-2char.png)
`US:RI` |  ![US:RI](img/sprite/bubble-wrap-style/shields-usa/2x/US:RI-2char.png) | ![US:RI](img/sprite/walkabout-style/shields-usa/2x/US:RI-2char.png) | ![US:RI](img/sprite/refill-style/shields-usa/2x/US:RI-2char.png) | ![US:RI](img/sprite/refill-style/shields-usa/2x/US:RI-2char.png)
`US:SC` |  ![US:SC](img/sprite/bubble-wrap-style/shields-usa/2x/US:SC-2char.png) | ![US:SC](img/sprite/walkabout-style/shields-usa/2x/US:SC-2char.png) | ![US:SC](img/sprite/refill-style/shields-usa/2x/US:SC-2char.png) | ![US:SC](img/sprite/refill-style/shields-usa/2x/US:SC-2char.png)
`US:SD` |  ![US:SD](img/sprite/bubble-wrap-style/shields-usa/2x/US:SD-2char.png) | ![US:SD](img/sprite/walkabout-style/shields-usa/2x/US:SD-2char.png) | ![US:SD](img/sprite/refill-style/shields-usa/2x/US:SD-2char.png) | ![US:SD](img/sprite/refill-style/shields-usa/2x/US:SD-2char.png)
`US:TN` |  ![US:TN](img/sprite/bubble-wrap-style/shields-usa/2x/US:TN-2char.png) | ![US:TN](img/sprite/walkabout-style/shields-usa/2x/US:TN-2char.png) | ![US:TN](img/sprite/refill-style/shields-usa/2x/US:TN-2char.png) | ![US:TN](img/sprite/refill-style/shields-usa/2x/US:TN-2char.png)
`US:TX` |  ![US:TX](img/sprite/bubble-wrap-style/shields-usa/2x/US:TX-2char.png) | ![US:TX](img/sprite/walkabout-style/shields-usa/2x/US:TX-2char.png) | ![US:TX](img/sprite/refill-style/shields-usa/2x/US:TX-2char.png) | ![US:TX](img/sprite/refill-style/shields-usa/2x/US:TX-2char.png)
`US:US` |  ![US:US](img/sprite/bubble-wrap-style/shields-usa/2x/US:US-2char.png) | ![US:US](img/sprite/walkabout-style/shields-usa/2x/US:US-2char.png) | ![US:US](img/sprite/refill-style/shields-usa/2x/US:US-2char.png) | ![US:US](img/sprite/refill-style/shields-usa/2x/US:US-2char.png)
`US:US:Alternate` |  ![US:US:Alternate](img/sprite/bubble-wrap-style/shields-usa/2x/US:US:Alternate-2char.png) | ![US:US:Alternate](img/sprite/walkabout-style/shields-usa/2x/US:US:Alternate-2char.png) | ![US:US:Alternate](img/sprite/refill-style/shields-usa/2x/US:US:Alternate-2char.png) | ![US:US:Alternate](img/sprite/refill-style/shields-usa/2x/US:US:Alternate-2char.png)
`US:US:Business` |  ![US:US:Business](img/sprite/bubble-wrap-style/shields-usa/2x/US:US:Business-2char.png) | ![US:US:Business](img/sprite/walkabout-style/shields-usa/2x/US:US:Business-2char.png) | ![US:US:Business](img/sprite/refill-style/shields-usa/2x/US:US:Business-2char.png) | ![US:US:Business](img/sprite/refill-style/shields-usa/2x/US:US:Business-2char.png)
`US:US:Truck` |  ![US:US:Truck](img/sprite/bubble-wrap-style/shields-usa/2x/US:US:Truck-2char.png) | ![US:US:Truck](img/sprite/walkabout-style/shields-usa/2x/US:US:Truck-2char.png) | ![US:US:Truck](img/sprite/refill-style/shields-usa/2x/US:US:Truck-2char.png) | ![US:US:Truck](img/sprite/refill-style/shields-usa/2x/US:US:Truck-2char.png)
`US:UT` |  ![US:UT](img/sprite/bubble-wrap-style/shields-usa/2x/US:UT-2char.png) | ![US:UT](img/sprite/walkabout-style/shields-usa/2x/US:UT-2char.png) | ![US:UT](img/sprite/refill-style/shields-usa/2x/US:UT-2char.png) | ![US:UT](img/sprite/refill-style/shields-usa/2x/US:UT-2char.png)
`US:VA` |  ![US:VA](img/sprite/bubble-wrap-style/shields-usa/2x/US:VA-2char.png) | ![US:VA](img/sprite/walkabout-style/shields-usa/2x/US:VA-2char.png) | ![US:VA](img/sprite/refill-style/shields-usa/2x/US:VA-2char.png) | ![US:VA](img/sprite/refill-style/shields-usa/2x/US:VA-2char.png)
`US:VT` |  ![US:VT](img/sprite/bubble-wrap-style/shields-usa/2x/US:VT-2char.png) | ![US:VT](img/sprite/walkabout-style/shields-usa/2x/US:VT-2char.png) | ![US:VT](img/sprite/refill-style/shields-usa/2x/US:VT-2char.png) | ![US:VT](img/sprite/refill-style/shields-usa/2x/US:VT-2char.png)
`US:WA` |  ![US:WA](img/sprite/bubble-wrap-style/shields-usa/2x/US:WA-2char.png) | ![US:WA](img/sprite/walkabout-style/shields-usa/2x/US:WA-2char.png) | ![US:WA](img/sprite/refill-style/shields-usa/2x/US:WA-2char.png) | ![US:WA](img/sprite/refill-style/shields-usa/2x/US:WA-2char.png)
`US:WI` |  ![US:WI](img/sprite/bubble-wrap-style/shields-usa/2x/US:WI-2char.png) | ![US:WI](img/sprite/walkabout-style/shields-usa/2x/US:WI-2char.png) | ![US:WI](img/sprite/refill-style/shields-usa/2x/US:WI-2char.png) | ![US:WI](img/sprite/refill-style/shields-usa/2x/US:WI-2char.png)
`US:WV` |  ![US:WV](img/sprite/bubble-wrap-style/shields-usa/2x/US:WV-2char.png) | ![US:WV](img/sprite/walkabout-style/shields-usa/2x/US:WV-2char.png) | ![US:WV](img/sprite/refill-style/shields-usa/2x/US:WV-2char.png) | ![US:WV](img/sprite/refill-style/shields-usa/2x/US:WV-2char.png)
`US:WY` |  ![US:WY](img/sprite/bubble-wrap-style/shields-usa/2x/US:WY-2char.png) | ![US:WY](img/sprite/walkabout-style/shields-usa/2x/US:WY-2char.png) | ![US:WY](img/sprite/refill-style/shields-usa/2x/US:WY-2char.png) | ![US:WY](img/sprite/refill-style/shields-usa/2x/US:WY-2char.png)
`county_shield` |  ![county_shield](img/sprite/bubble-wrap-style/shields-usa/2x/county_shield-2char.png) | ![county_shield](img/sprite/walkabout-style/shields-usa/2x/county_shield-2char.png) | ![county_shield](img/sprite/refill-style/shields-usa/2x/county_shield-2char.png) | ![county_shield](img/sprite/refill-style/shields-usa/2x/county_shield-2char.png)

## Versions

The following Mapzen basemap styles support the `mapzen_icon_library` style defaults and named shield assets:

* Bubble Wrap: `10.0.0` and later
* Cinnabar: `10.0.0` and later
* Refill: `12.0.0` and later
* Walkabout: `8.0.0` and later

Earlier versions of Mapzen basemap styles did not support all shields in the table above or the style defaults.

The following style does not support the shields:

* Tron: `6.0.0` or earlier