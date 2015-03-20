
# TianDiTu

----

<link type="text/css" rel="stylesheet" href="../spm_modules/leaflet/0.7.3/leaflet.css" />

<div id="map" style="height: 300px;"></div>

````js
seajs.use(['jquery', 'leaflet', 'leaflet-providers', '../src/leaflet.chinesetmsproviders'], function($, L) {
  var normalm = L.tileLayer.chinaProvider('TianDiTu.Normal.Map',{maxZoom:18,minZoom:5}),
      normala = L.tileLayer.chinaProvider('TianDiTu.Normal.Annotion',{maxZoom:18,minZoom:5}),
      imgm = L.tileLayer.chinaProvider('TianDiTu.Satellite.Map',{maxZoom:18,minZoom:5}),
      imga = L.tileLayer.chinaProvider('TianDiTu.Satellite.Annotion',{maxZoom:18,minZoom:5});

  var normal = L.layerGroup([normalm,normala]),
      image = L.layerGroup([imgm,imga]);

  var baseLayers = {
      "地图":normal,
      "影像":image,
  }

  var overlayLayers = {

  }

  var map = L.map("map",{
      center:[31.59, 120.29],
      zoom:12,
      layers:[normal],
      zoomControl:false
  });

  L.control.layers(baseLayers,overlayLayers).addTo(map);
  L.control.zoom({zoomInTitle:'放大', zoomOutTitle:'缩小'}).addTo(map);
})
````
