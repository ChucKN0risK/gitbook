---
description: "Types define every type of design token and asset Specify is compatible with. Use them to target specific types of design data you want to pull from Specify and manage with\_rules and parsers."
---

# Token types

## Border

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

## Bitmap
Bitmaps are raster images you can use in many contexts. They're basically any image you can display in a UI that is a .png, .jpeg, .webp, .avif...

```typescript
interface BitmapValue {
  url: string;
  dimension?: number;
  format?: string;
}
```

## Color
Colors have meaning and support the purpose of the content, communicating things like hierarchy of information, interactive states, and the difference between distinct elements in your UI. Among all your design token types, color is surely one of the most important ones.

```typescript
interface ColorValue {
  r: number;
  g: number;
  b: number;
  a: number;
}
```

## Depth
The Depth token type sets a UI element's position on the z-axis. More commonly called z-index on [Web ↗](https://developer.mozilla.org/en-US/docs/Web/CSS/z-index) and zIndex on [Android ↗](https://developer.android.com/reference/kotlin/androidx/compose/ui/package-summary#(androidx.compose.ui.Modifier).zIndex(kotlin.Float)) and [iOS ↗](https://developer.apple.com/documentation/uikit/uicollectionviewlayoutattributes/1617768-zindex).