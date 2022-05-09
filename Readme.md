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

Rendering with shadows needs a lot of calculation. It is a common technique to select objects which capture or receive shadows in a scene. But `KHR_lights_punctual` extension has the capability of defining lights but doesn't have the capability of defining shadows. To determine what nodes in a scene should capture or receive shadows is the responsibility of applications or engines.

This `KHR_lights_shadows` extension provides a way to let applications or engines know what nodes should capture or receive shadows.

## Example screenshot

T.B.D.

## Adding shadows to Nodes

```
"nodes": [
    {
        "mesh": 0,
        "extensions": {
            "KHR_lights_shadows": {
                "receive": true
            }
        }
    },
    {
        "mesh": 1,
        "extensions": {
            "KHR_lights_shadows": {
                "capture": true
            }
        }
    }
]
```

## Shadow Node Types

| Property | Type | Description | Requires |
|:------|:------|:------|:------|
| `capture` | `boolean` | Whether the node captures shadows | No, default: `false` |
| `receive` | `boolean` | Whether the node receives shadows | No, default: `false` |


## Implementation Note

T.B.D.
