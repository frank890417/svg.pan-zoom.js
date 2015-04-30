svg.pan-zoom.js
===============
A JavaScript library for panning and zooming SVG things.

[![](http://i.imgur.com/jbJJFHE.jpg)](http://jillix.github.io/svg.pan-zoom.js/)

## Available on CDN!

[**CDNJS** kindly hosts this library](https://cdnjs.com/libraries/svg.pan-zoom.js). You can use the cdn version:

```html
<script src="https://cdnjs.cloudflare.com/ajax/libs/svg.pan-zoom.js/2.1.0/svg.pan-zoom.min.js"></script>
```

## Usage
This library depends on the [SVG.js](https://github.com/wout/svg.js) library.

```html
<script src="path/to/svg.js"></script>
<script src="path/to/svg.pan-zoom.js"></script>
<!-- Or from cdn
<script src="https://cdnjs.cloudflare.com/ajax/libs/svg.pan-zoom.js/2.1.0/svg.pan-zoom.min.js"></script>
-->
<script>
    var svg = new SVG($(".graph").get(0)).size("100%", 900);
    var links = svg.group();
    var markers = svg.group();
    var nodes = svg.group();

    // Add draggable circles
    var g1 = nodes.group().translate(300, 200).draggable();
    g1.circle(80).fill("#C2185B");

    var g2 = nodes.group().translate(100, 200).draggable();
    g2.circle(50).fill("#E91E63");

    var g3 = nodes.group().translate(200, 400).draggable();
    g3.circle(100).fill("#FF5252");

    // Make the group pannable and zoomable
    nodes.panZoom();
</script>
```

Check out [the online demo](http://jillix.github.io/svg.pan-zoom.js/).

## Documentation
### `panZoom(opt_options)`
The pan-zoom contructor.

#### Params
- **Object** `opt_options`: An optional object containing the following fields:
 - `zoom` (Array): An array of two float values: the minimum and maximum zoom values (default: `undefined`).

#### Return
- **PanZoom** The PanZoom object containing the following fields:
 - `elm` (SVG): The selected element.
 - `pan` (Object): An object containing pan values.
 - `transform` (Object): An object containing the transform data (`scaleX`, `scaleY`, `x` and `y`).

### `setPosition(x, y, z)`
Sets the graph position programatically.

#### Params
- **Number** `x`: The relative position to the svg document (on x axis).
- **Number** `y`: The relative position to the svg document (on y axis).
- **Number** `z`: The zoom value which will be handled as `scale` internally.

#### Return
- **PanZoom** The `PanZoom` instance.

### `zoom(z)`
Zooms in/out the graph programatically.

#### Params
- **Number** `z`: The zoom value which will be handled as `scale` internally.

#### Return
- **PanZoom** The `PanZoom` instance.

## How to contribute
1. File an issue in the repository, using the bug tracker, describing the
   contribution you'd like to make. This will help us to get you started on the
   right foot.
2. Fork the project in your account and create a new branch:
   `your-great-feature`.
3. Commit your changes in that branch.
4. Open a pull request, and reference the initial issue in the pull request
   message.

## License
See the [LICENSE](./LICENSE) file.
