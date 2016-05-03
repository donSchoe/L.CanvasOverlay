### L.CanvasOverlay

Leaflet Canvas Overlay is a straightforward full screen canvas overlay class
that calls custom user function for gl drawing.

**Requires**
  - Leaflet 1.0.0rc1 or later


### Usage

Leaflet Full view Canvas Overlay - straightforward full screen canvas overlay that calls custom user function for drawing.
Mostly extracted from [here](https://github.com/Leaflet/Leaflet.heat) added resize and few other parameters for callback
Compare to same data SVG rendering [here](http://bl.ocks.org/Sumbera/7e8e57368175a1433791)

    //Example:
    L.canvasOverlay()
       .params({data: points})     // optional add any custom data that will be passed to draw function
             .drawing(drawingOnCanvas)   // set drawing function
             .addTo(leafletMap);         // add this layer to leaflet map


    //Custom drawing function:
      function drawingOnCanvas(canvasOverlay, params) {
                var ctx = params.canvas.getContext('2d');
                params.options.data.map(function (d, i) {
                  // canvas drawing goes here
                });
            };

    // parameters passed to custom draw function :
     {
                                    canvas   : <canvas>,
                                    bounds   : <bounds in WGS84>
                                    size     : <view size>,
                                    zoomScale: <zoom scale is  1/resolution>,
                                    zoom     : <current zoom>,
                                    options  : <options passed >
                 };

Other useful full view  Leaflet Canvas sources here:
- [leaflet.heat](https://github.com/Leaflet/Leaflet.heat)
- [Full Canvas](https://github.com/cyrilcherian/Leaflet-Fullcanvas)
- [CartoDb Leaflet.Canvas](https://github.com/CartoDB/Leaflet.CanvasLayer)

Read more:
- http://blog.sumbera.com/2014/04/20/leaflet-canvas/
- http://bl.ocks.org/sumbera/11114288

```
  /* setup leaflet canvas webgl overlay */
  ovl = L.canvasOverlay().drawing(drawGL).addTo(map);
  cnv = ovl.canvas()
  ovl.canvas.width = cnv.clientWidth;
  ovl.canvas.height = cnv.clientHeight;
```

... where `drawGL()` is your custom user draw function.


### Copyright & License

Originally (C) 2014 Stanislav Sumbera

Maintained by Alexander Schoedon <schoedon@uni-potsdam.de>

MIT and Credits attached.


### Credits

Originally hosted on Gist:
  - https://gist.github.com/Sumbera/11114288

Inspired and portions taken from:
  - https://github.com/Leaflet/Leaflet.heat
