# IrisBiome
> Represents a biome in iris.
```json
{
    "biomeSkyScatter": [],
    "children": [],
    "decorators": [],
    "objects": [],
    "name": "A Biome",
    "biomeZoom": 1,
    "layers": [{
        "minHeight": 1,
        "terrainZoom": 5,
        "maxHeight": 1,
        "palette": ["GRASS_BLOCK"],
        "dispersion": "SCATTER"
    }],
    "generators": [{
        "min": 0,
        "max": 0,
        "generator": "default"
    }],
    "childShrinkFactor": 1.5,
    "biomeDispersion": "SCATTER",
    "derivative": "THE_VOID",
    "biomeScatter": []
}
```

## name
> This is the human readable name for this biome. This can and should be different than the file name. This is not used for loading biomes in other objects.

## biomeDispersion
> This changes the dispersion of the biome colors if multiple derivatives are chosen

## biomeZoom
> This zooms in the biome colors if multiple derivatives are chosen

## derivative
> The raw derivative of this biome. This is required or the terrain will not properly generate. Use any vanilla biome type. Look in examples/biome-list.txt

## biomeScatter
> You can instead specify multiple biome derivatives to randomly scatter colors in this biome

## biomeSkyScatter
> Since 1.13 supports 3D biomes, you can add different derivative colors for anything above the terrain. (Think swampy tree leaves with a desert looking grass surface)

## childShrinkFactor
> If this biome has children biomes, and the gen layer chooses one of this biomes children, how much smaller will it be (inside of this biome). Higher values means a smaller biome relative to this biome's size. Set higher than 1.0 and below 3.0 for best results.

## children
> List any biome names (file names without.json) here as children. Portions of this biome can sometimes morph into their children. Iris supports cyclic relationships such as A > B > A > B. Iris will stop checking 9 biomes down the tree.

## layers
> This defines the layers of materials in this biome. Each layer has a palette and min/max height and some other properties. Usually a grassy/sandy layer then a dirt layer then a stone layer. Iris will fill in the remaining blocks below your layers with stone.

## decorators
> Decorators are used for things like tall grass, bisected flowers, and even kelp or cactus (random heights)

## objects
> Objects define what schematics (iob files) iris will place in this biome

## generators
> Generators for this biome. Multiple generators with different interpolation sizes will mix with other biomes how you would expect. This defines your biome height relative to the fluid height. Use negative for oceans.
