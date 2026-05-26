---
layout: default
title: LLMMaterial
has_children: true
nav_order: 2
---

# LLMMaterial

JSON-driven UE5 Material Asset Generation System. Define material node graphs in JSON, AI outputs `.llmmat` files, and the system automatically generates compilable Material Blueprint assets.

## Core Features

- JSON ↔ Material bidirectional conversion
- Full Expression node support (30+ types)
- UE5 Substrate BSDF material support
- Custom HLSL function (.ush) generation
- Automatic node layout (Sugiyama algorithm)
- In-editor panel, import/preview/generate
- SubsurfaceProfile skin materials
- Texture parameter and sampling support
- Material Domain and Blend Mode configuration
- Schema-driven type system

## Quick Preview

```json
{
  "version": "1.0",
  "name": "RedMetal",
  "domain": "Surface",
  "shadingModel": "DefaultLit",
  "nodes": [
    { "id": "color", "type": "Constant3Vector",
      "properties": { "Constant": [1.0, 0.0, 0.0] }}
  ],
  "output": {
    "baseColor": { "node": "color", "pin": "Result" }
  }
}
```

## Supported Material Types

| Category | Supported Content |
|----------|------------------|
| Domain | Surface, PostProcess, UserInterface, VirtualTexture |
| BlendMode | Opaque, Masked, Translucent, Additive, Modulate |
| ShadingModel | DefaultLit, Unlit, Subsurface, SubsurfaceProfile, ClearCoat, Hair, Cloth, Eye, Strata |
| Substrate | SubstrateSlabBSDF, SubstrateHairBSDF, VerticalLayering, HorizontalMixing |

## Next Steps

- [Getting Started](getting-started.html) - Installation and basic usage
- [Node Types](node-types.html) - All supported nodes
- [Substrate](substrate.html) - UE5 Substrate materials
- [Examples](examples.html) - Various material type examples
