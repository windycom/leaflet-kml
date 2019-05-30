# Leaflet KML layer plugin

![Example](assets/screenshot.jpg)

Demo: https://www.windy.com/uploader

This plugin was extracted from Pavel Shramov's Leaflet Plugins [repository](https://github.com/shramov/leaflet-plugins) in order to maintain this code more frequently and separate KML layer from other plugins.

So far we have fixed few issues.

Probablly will work on Leaflet 1+, tested on Leaflet 1.4.

## How to use

 ```html
<html>
<head>
	<link rel="stylesheet" href="http://unpkg.com/leaflet@1.3.1/dist/leaflet.css" />
	<script src="http://unpkg.com/leaflet@1.3.1/dist/leaflet.js"></script>
	<script src="./L.KML.js"></script>
</head>
<body>
	<div style="width:100%; height:100%" id="map"></div>
	<script type='text/javascript'>
		var map = new L.Map('map', {center: new L.LatLng(58.4, 43.0), zoom: 11});
		var osm = new L.TileLayer('http://{s}.tile.openstreetmap.org/{z}/{x}/{y}.png');
		var track = new L.KML("assets/example1.kml", {async: true});
		track.on("loaded", function(e) {
			map.fitBounds(e.target.getBounds());
		});
		map.addLayer(track);
		map.addLayer(osm);
	</script>
</body>
</html>
```

## Changelog

 * 1.0.0 - Initial commit, original version with few fixes

## Licence

MIT
