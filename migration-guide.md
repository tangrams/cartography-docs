# Migration guide

## Named label variants

The standalone basemap label variants `no-labels` and `more-labels` were fully deprecated in September 2017. The following versions require importing the default `{basemap}-style` and then add or remove labels by also importing a **label** theme.

- Bubble Wrap: `8.0.0`
- Cinnabar: `8.0.0`
- Refill: `9.0.0`
- Tron: `5.0.0`
- Walkabout: `6.0.0`

For example, the following Walkabout label variants in version 5 and earlier releases map to new theme-based label steps in version 6:


| Walkabout label variant       | label |
|-------------------------------|------:|
| `walkabout-style` _(default)_ | 5     |
| `walkabout-style-no-labels`   | 0     |
| `walkabout-style-more-labels` | 10    |

The two named Walkabout label variants `walkabout-style-no-labels` or `walkabout-style-more-labels` available in version 5 ane earlier are no longer supported directly – you need up upgrade to version 8 and import the label theme, like:

Example **Tangram YAML** usage:

```
import:
    # basemap style
    - https://mapzen.com/carto/walkabout-style/6/walkabout-style.zip
    # add more labels with a theme
    - https://mapzen.com/carto/walkabout-style/6/themes/label-10.zip
```

## Zinc

The standalone Zinc basemap style was deprecated in September 2017 at version `6.1.0`. But we continue to support Zinc now as a [Refill color theme](thmes.md#Refill) starting in Refill `9.0.0`.

Example **Tangram YAML** usage:

```
import:
    # basemap style
    - https://mapzen.com/carto/refill-style/9/refill-style.zip
    # change the colors to Zinc
    - https://mapzen.com/carto/refill-style/9/themes/color-zinc.zip
```
