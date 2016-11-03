# Versioning

When a new version of a Mapzen House Style or icon packs are released, developers should be able to tell from the version increment how much effort it will take them to integrate the new basemap with their map. We use semantic versioning to communicate this.

## What is Semantic Versioning?

Semantic versioning (or [SemVer](http://semver.org/)) is a formalized way of making promises with an X.Y.Z version indicator.

### Version components

- `MAJOR`.`MINOR`.`PATCH`, example: `1.0.0`

### Version parts:

1. **MAJOR** version **X** for incompatible API changes.
2. **MINOR** version **Y** when adding functionality in a backwards-compatible manner, and
3. **PATCH** version **Z** when fixing backwards-compatible bugs

### Developer level of effort:

- Major version X: **high** – significant integration challenges, read the changelog closely
- Minor version Y: **low** – some integration challenges, read the changelog
- Bug fixes Z: **none** – simply use the new tiles, skim or ignore the changelog

## Import strategy

**MAJOR versions**

As Mapzen's house styles are still in active development we recommend peggging an import to a specific major version, eg: `5`, so you enjoy any minor and patch updates but are ensured of stable named scene elements.

```
import: https://mapzen.com/carto/refill-style-more-labels/5/refill-style-more-labels.yaml
```

**LATEST versions**

We only recommend pegging to the **latest** vesion if you are not modifying documented API scene elements.

```
import: https://mapzen.com/carto/refill-style-more-labels/refill-style-more-labels.yaml
```

**MINOR versions**

We don't recommend pegging to a **minor** vesion.

**PATCH versions**

We don't recommend pegging to a **patch** vesion.


## Promises

### MAJOR version increments:

1. **Remove** global `property`
1. **Change** global `property` **name** or default value
1. **Remove** draw `layer`
1. **Change** draw `layer` **name**
1. **Remove** draw  `style`
1. **Change** draw `style` **name**
1. **Remove** `sprite` icon
1. **Change** `sprite` icon **name**
1. Requires new **major** version of **Tangram** (or minor version if before 1.0)
1. Requires new **major** version of **Mapzen Vector Tiles**
1. Requires new **minor** version of **Mapzen Vector Tiles** when recommended map sandwich feature order values change.

### MINOR version increments:

1. **Add** global `property`
1. **Add** draw `layer`
1. **Add** draw `style`
1. **Add** `sprite` icon
1. **Change** draw `style` default visual appearance
1. **Remove** `sprite` icon
1. **Change** `sprite` icon **name**
1. **Change** `sprite` icon asset
1. **Change** to scene elements not documented by API reference
1. Requires new **minor** version of **Tangram** (or patch version if before 1.0)
1. Requires new **minor** version of **Mapzen Vector Tiles**

### PATCH version increments

1. **Correct** a regression in a documented scene element (to the last good version)
1. **Correct** a newly added global `property` **name** or default value
1. **Correct** a newly added draw `layer` **name**
1. **Correct** a newly added draw `style` **name** or default visual appearance
1. **Correct** a newly added `sprite` icon **name** or asset
1. Bug fix **change** to scene elements not documented by API reference
1. Requires new **patch** version of **Mapzen Vector Tiles**

## See also

- [semver.org](http://semver.org)
- [Tilezen versioning](https://github.com/tilezen/vector-datasource/blob/master/SEMANTIC-VERSIONING.md)
- [Natural Earth versioning](https://github.com/nvkelso/natural-earth-vector/blob/master/README.md)
- [Who's On First](https://github.com/whosonfirst/whosonfirst-placetypes#roles)
