# Leaflet-Ruler Plugin

A simple leaflet plugin to measure **true bearing** and **distance** between clicked points. Extends L.Control.

### [Demo](http://gokertanrisever.github.io/leaflet-ruler)
[![Demo](https://raw.githubusercontent.com/gokertanrisever/leaflet-ruler/master/examples/leaflet-ruler-demo.png)](http://gokertanrisever.github.io/leaflet-ruler)

## Requirements
- Leaflet 1.0.0+

## Usage

- Create a [leaflet map](http://leafletjs.com/examples/quick-start/)
- Include leaflet-ruler.js and leaflet-ruler.css files.
```
<link rel="stylesheet" type="text/css" href="https://rawgit.com/gokertanrisever/leaflet-ruler/master/leaflet-ruler.css">
<script src="https://rawgit.com/gokertanrisever/leaflet-ruler/master/leaflet-ruler.js"></script>
```
- Add Ruler control to map
```
L.control.ruler().addTo(map);
```
- Double-click finishes measurement path and starts a new measurement.
- Escape button also finishes measurement path. Second push to escape turns off the plugin.
- It's possible to add other units. No need to specify any option value to use default.
```
var options = {
          position: 'topleft',
          lengthUnit: {
            factor: 0.539956803,    //  from km to nm
            display: 'Nautical Miles',
            decimal: 2
          }
        };
L.control.ruler(options).addTo(map);
```
 

## Default Options

```
options: {
      position: 'topright',         // Leaflet control position option
      circleMarker: {               // Leaflet circle marker options for points used in this plugin
        color: 'red',
        fillColor: '#ffffff',
        fillOpacity: 0.5,
        radius: 2
      },
      lineStyle: {                  // Leaflet polyline options for lines used in this plugin
        color: 'red',
        dashArray: '1,6'
      },
      lengthUnit: {                 // You can use custom length units. Default unit is kilometers.
        display: 'km',              // This is the display value will be shown on the screen. Example: 'meters'
        decimal: 2,                 // Distance result will be fixed to this value. 
        factor: null                // This value will be used to convert from kilometers. Example: 1000 (from kilometers to meters)  
      },
      angleUnit: {
        display: '&deg;',           // This is the display value will be shown on the screen. Example: 'Gradian'
        decimal: 2,                 // Bearing result will be fixed to this value.
        factor: null                // This option is required to customize angle unit. Specify solid angle value for angle unit. Example: 400 (for gradian).
      }
    }
```

