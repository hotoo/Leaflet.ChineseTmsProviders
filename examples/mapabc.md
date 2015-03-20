
# MapABC

----

<link type="text/css" rel="stylesheet" href="../spm_modules/leaflet/0.7.3/leaflet.css" />

<div id="map" style="height: 300px;"></div>

````js
seajs.use(['jquery', 'leaflet', 'leaflet-providers', '../src/leaflet.chinesetmsproviders'], function($, L) {
  var normalm = L.tileLayer.chinaProvider('MapABC.Normal.Map',{maxZoom:18,minZoom:5});

  var map = L.map("map",{
      center:[31.59, 120.29],
      zoom:12,
      layers:[normalm],
      zoomControl:false
  });

  L.control.zoom({zoomInTitle:'放大', zoomOutTitle:'缩小'}).addTo(map);
})
````
