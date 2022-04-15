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

## Example screenshot

T.B.D.

## Defining Shadows

T.B.D.

```
"extensions": {
    "KHR_lights_shadows": {
        "type": "pcf"
    }
}
```

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

## Shadow Types

| Property | Type | Description | Requires |
|:------|:------|:------|:------|
| `type` | `string` | Shadows type | No, default: `pcf` |

## Shadow Types for Nodes

| Property | Type | Description | Requires |
|:------|:------|:------|:------|
| `capture` | `boolean` | Whether the node captures shadows | No, default: `false` |
| `receive` | `boolean` | Whether the node receives shadows | No, default: `false` |


## Implementation Note

T.B.D.