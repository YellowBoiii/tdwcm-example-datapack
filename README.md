![image](posterV2.png)


# Example: TARDIS Chameleon Datapack

This README explains the example datapack configuration in `data/example/tdwcm/tardis_chameleon/example.json`. It adds a Chameleon with the ID `example:example`.

## Example JSON

```json
{
  "name": "example",
  "display_name": "Example TARDIS",
  "description": "An example TARDIS added by a datapack",
  "credit": "TDWCM example pack",
  "size": [1.375, 2.0725, 0.9375, 0.125],
  "door_sound": "default",
  "variants": [""],
  "exterior_portal_close_ticks": 5,
  "interior_portal_close_ticks": 5,
  "interior_view_depth": 0.75
}
```

## File location and ID

Place the JSON file at:

```text
data/<namespace>/tdwcm/tardis_chameleon/<id>.json
```

The namespace comes from the directory under `data`, and the ID path comes from the JSON filename. In this example, the namespace is `example` and the filename is `example.json`, so the Chameleon ID is `example:example`.

## Fields

| Field | Required | Description |
|---|---:|---|
| `name` | No | Internal Chameleon name. If omitted, the JSON filename is used. |
| `display_name` | No | Name shown to players. |
| `description` | No | Description shown in the Chameleon Circuit. |
| `credit` | No | Author or datapack credit shown in the interface. |
| `size` | Yes | Exterior dimensions: `[width, height, door_distance, door_step]`. |
| `interior_size` | No | Interior dimensions in the same format as `size`. Defaults to the exterior dimensions, with a door step of `0`. |
| `door_sound` | Yes | Door sound ID, for example `"default"`. |
| `interior_door_sound` | No | Sound ID for the interior door. |
| `variants` | No | List of variants available in the Chameleon Circuit. |
| `exterior_portal_close_ticks` | No | Exterior portal closing delay in ticks. Range: `0`–`1200`; default: `5`. |
| `interior_portal_close_ticks` | No | Interior portal closing delay in ticks. Range: `0`–`1200`; default: `5`. |
| `interior_view_depth` | No | Interior view depth. Range: `0`–`16`; default: `0.75`. |

## Variant display names

A variant can be specified as a string:

```json
"variants": ["massacre"]
```

## Example resource pack

For the example's `"name": "example"`, resource files use the `tdwcm` asset namespace and these paths:

```text
assets/tdwcm/geo/tardis/tardis_example/tardis_example.geo.json
assets/tdwcm/textures/entity/tardis/tardis_example/tardis_example.png
assets/tdwcm/animations/tardis/tardis_example/tardis_example.animation.json

assets/tdwcm/geo/tardis/tardis_example/tardis_door_example.geo.json
assets/tdwcm/textures/entity/tardis/tardis_example/tardis_door_example.png
assets/tdwcm/animations/tardis/tardis_example/tardis_door_example.animation.json
```

Only include the files your Chameleon needs; assets without a variant-specific file fall back to the base Chameleon asset. For a variant named `hartnell`, variant assets go in a `hartnell` subfolder and include `_hartnell` in the filename, for example:

```text
assets/tdwcm/geo/tardis/tardis_example/hartnell/tardis_example_hartnell.geo.json
assets/tdwcm/textures/entity/tardis/tardis_example/hartnell/tardis_example_hartnell.png
assets/tdwcm/animations/tardis/tardis_example/hartnell/tardis_example_hartnell.animation.json
```

Door assets for variants use the same subfolder and suffix pattern, for example `tardis_door_example_hartnell.geo.json`. A variant's `display_name` only changes its label in the interface; it does not change resource filenames.

The resource pack should have a `pack.mcmeta` at its root and the `assets` directory alongside it. Enable both the datapack and resource pack in the world. Use `/reload` after changing datapack data; resource pack changes may require reloading resource packs with `F3+T` or rejoining the world.


Run `/reload` in-game after adding or changing datapack files.
