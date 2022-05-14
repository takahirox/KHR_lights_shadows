# KHR\_lights\_shadows

## Contributors

* Takahiro Aoyagi, Mozilla, [@takahirox](https://github.com/takahirox)

## Status

Draft

## Dependencies

Written against the glTF 2.0 spec and
[`KHR_lights_punctual`](https://github.com/KhronosGroup/glTF/tree/main/extensions/2.0/Khronos/KHR_lights_punctual).

## Overview

This `KHR_lights_shadows` extension defines what nodes cast or receive shadows
and what lights cast shadows against
[`KHR_lights_punctual`](https://github.com/KhronosGroup/glTF/tree/main/extensions/2.0/Khronos/KHR_lights_punctual).

Rendering with shadows needs a lot of calculation. It is a common technique to
select objects which cast or receive shadows in a scene. But
`KHR_lights_punctual` extension has the capability of defining lights but doesn't
have the capability of defining shadows. To determine what nodes in a scene
should cast or receive shadows is the responsibility of applications or engines.

This `KHR_lights_shadows` extension provides a way to let applications or
engines know what nodes should cast or receive shadows and what lights should
cast shadows.

## Example screenshot

T.B.D.

## Cast/Receive shadows for Meshes

Whether a mesh node casts shadows and whether it receives shadows are defined by
adding `extensions.KHR_lights_shadows` property to a `node`, having `mesh`
property, with `cast` and `receive` boolean properties inside it.


```
"nodes": [{
    "mesh": 0,
    "extensions": {
        "KHR_lights_shadows": {
            "cast": false,
            "receive": true
        }
    }
}, {
    "mesh": 1,
    "extensions": {
        "KHR_lights_shadows": {
            "cast": true,
            "receive": false
        }
    }
}]
```

## Turn on/off shadows for Lights

Whether a light node casts shadows is defined by adding
`extensions.KHR_lights_punctual.extensions.KHR_lights_shadows` property to a
`node`, having `extensions.KHR_lights_punctual.light` property, with `cast`
boolean property inside it.

```
"nodes": [{
    "extensions": {
        "KHR_lights_punctual": {
            "light": 0,
            "extensions": {
                "KHR_lights_shadows": {
                    "cast": true
                }
            }
        }
    }
}]
```

## Cast/Receive Shadows properties for Mesh

| Property | Type | Description | Requires |
|:------|:------|:------|:------|
| `cast` | `boolean` | Whether the mesh node casts shadows | No, default: `true` |
| `receive` | `boolean` | Whether the mesh node receives shadows | No, default: `true` |

## Cast shadows property for Light

| Property | Type | Description | Requires |
|:------|:------|:------|:------|
| `cast` | `boolean` | Whether the light node casts shadows | No, default: `true` |

## Implementation Note

This extension doesn't define shadow rendering techniques (ie. Shadow Map) or
shadow types (ie. PCF). They should be application or engine specific.

`cast` and `receive` properties for Meshes don't define whether the mesh node is
visible. Similarly `cast` property for Lights doesn't define whether the light
is active.
