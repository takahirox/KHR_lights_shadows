# KHR\_lights\_shadows

## Contributors

* Takahiro Aoyagi, Mozilla, [@takahirox](https://github.com/takahirox)

## Status

Draft

## Dependencies

Written against the glTF 2.0 spec and [`KHR_lights_punctual`](https://github.com/KhronosGroup/glTF/tree/main/extensions/2.0/Khronos/KHR_lights_punctual).

## Overview

`KHR_lights_shadows` is a glTF extension which allows you to configure shadows against
[`KHR_lights_punctual`](https://github.com/KhronosGroup/glTF/tree/main/extensions/2.0/Khronos/KHR_lights_punctual).

Rendering with shadows needs a lot of calculation. It is a common technique to select objects which cast or receive shadows in a scene. But `KHR_lights_punctual` extension has the capability of defining lights but doesn't have the capability of defining shadows. To determine what nodes in a scene should cast or receive shadows is the responsibility of applications or engines.

This `KHR_lights_shadows` extension provides a way to let applications or engines know what nodes should cast or receive shadows.

## Example screenshot

T.B.D.

## Cast/Receive shadows for Meshes

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

## Cast/Receive Shadows for Mesh Types

| Property | Type | Description | Requires |
|:------|:------|:------|:------|
| `cast` | `boolean` | Whether the mesh node casts shadows | No, default: `true` |
| `receive` | `boolean` | Whether the mesh node receives shadows | No, default: `true` |

## Turn on/off shadows for Light Types

| Property | Type | Description | Requires |
|:------|:------|:------|:------|
| `cast` | `boolean` | Whether the light node casts shadows | No, default: `true` |

## Implementation Note

T.B.D.
