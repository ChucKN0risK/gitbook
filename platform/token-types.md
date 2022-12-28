---
description: "Types define every type of design token and asset Specify is compatible with. Use them to target specific types of design data you want to pull from Specify and manage with\_rules and parsers."
---

# Token types

### Border

A border is a line surrounding a UI element. According to your target platform capabilities, you can define the border to go inside (inner border), outside (outer border), or between them (center).

{% hint style="info" %}
Looking for Border radius? You can add them as a Measurement type.
{% endhint %}

```typescript
interface BorderValue {
  color: {
    value: ColorValue;
  };
  type:
    | 'none'
    | 'hidden'
    | 'dotted'
    | 'dashed'
    | 'solid'
    | 'double'
    | 'groove'
    | 'ridge'
    | 'inset'
    | 'outset';
  width: {
    value: MeasurementValue;
  };
  align?: string;
  radii?: MeasurementValue;
  rectangleCornerRadii?: Array<MeasurementValue>;
  dashes?: Array<MeasurementValue>;
}
```
