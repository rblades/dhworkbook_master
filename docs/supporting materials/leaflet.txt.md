# Making a map website with Leaflet.js

The [leaflet.js](http://leafletjs.com/) library allows you to create quite nice interactive maps in a web-browser, that are also mobile friendly. Here, we'll build a map that uses our georectified map as the base layer (rather than as an image overlay). I won't go into the details, but rather will provide you enough guidance to get going. The documentation for Leaflet is quite extensive, and many other tutorials abound.

## Setup
1\. Create a new github repository for this exercise. 
2\. Create a new branch called ```gh-pages```. We will be putting our html on the gh-pages branch, so that ```<your username>/github.io/<repo>map.html``` can serve us up the webpage when we're done.
3\. Leaflet comes with a number of [excellent tutorials](http://leafletjs.com/examples.html). We're going to look at the [first one](http://leafletjs.com/examples/quick-start.html). 
4\. Go to the [leaflet quick-start tutorial](http://leafletjs.com/examples/quick-start.html) and read through it carefully. In essence, you create a webpage that draws its instructions on how to handle geographic data and how to style that data from the leaflet.js source. That way, the browser knows how to render all the geographic information you're about to give it. 

Do you see where leaflet is calling on geographic information? This bit:

```javascript
L.tileLayer('http://{s}.tiles.mapbox.com/v3/MapID/{z}/{x}/{y}.png', {
    attribution: 'Map data &copy; <a href="http://openstreetmap.org">OpenStreetMap</a> contributors, <a href="http://creativecommons.org/licenses/by-sa/2.0/">CC-BY-SA</a>, Imagery © <a href="http://mapbox.com">Mapbox</a>',
    maxZoom: 18
}).addTo(map);
```
is calling on a background layer from the mapbox service. Instead of using mapbox, We can slot the url to the georectified map we made in module 4 in there! That is, swap out the url from the line beginning ```L.tileLayer```. You'd change the copyright notice, etc, too, obviously.

The other bits of code that create callouts, polygons, and so on, are all using decimal degrees to locate the drawn elements on top of that map.

This code:

```javascript
L.marker([51.5, -0.09]).addTo(map)
			.bindPopup("<b>Hello world!</b><br />I am a popup.").openPopup();
```

can be copied and repeated in the document, with new coordinates in decimal degrees for each new point. In the second line, between the quotation marks, you can use regular html to style your text, include pictures, and so on.

5\. In a new browser window, open the [example map for the quickstart guide](http://leafletjs.com/examples/quick-start/example.html).

6\. Right-click the page and select view source.

## So let's get started.
1. Create a new html document in your gh-pages branch of your repo.
2. Copy the html from the quickstart map (right-click and select 'view source' on this page: [leafletjs.com/examples/quick-start/example.html](leafletjs.com/examples/quick-start/example.html)
3. Paste the code in your new html document in your gh-pages branch of your repo. Call it 'map.html' and commit your changes.
4. Change the source map to point to a georectified map you made in module 4. Using the Ottawa Fire Insurance map I used as an example in module 4, I created [this map](http://shawngraham.github.io/exercise/leaflet-ottawa.html). Right click and view my page source to see what I changed up.  **NB You could keep the basic mapbox service base map, and render the Ottawa Fire Insurance map as an overlay [reference documentation]http://leafletjs.com/reference-1.0.3.html#imageoverlay). Or you could do a series of overlays, showing the change in the city over time. (My favourite example of a leaflet-powered historical map visualization is the [Slave Revolt in Jamaica project](http://revolt.axismaps.com/) by Vincent Brown). But you don't necessarily have to do this.**
5. Add a series of markers with historical information by duplicating and then changing up the ```L.marker``` settings to your own data. Commit your changes!

This all just makes the map. The rest of the webpage would have to be styled as you would normally for a webpage. That is, you'd probably want to add an explanation about what the map shows, how it was created, and how the user ought to interact with it, links to your source data, and so on. The easiest place to add all that kind of information would be between these two tags in the page source:

```html
</script>
</body>
```

### Going further
Let's say you have a whole bunch of information that you want to represent on the map. Perhaps it's in a well organized csv file, with a latitude and a longitude column in decimal degrees. Adding points one at a time to the map as described above would take ages. Instead, let's convert that csv to geojson, and then use [bootleaf](https://github.com/bmcbride/bootleaf) to make a map.

Bootleaf is a template that uses a common html template package, '[Bootstrap](http://getbootstrap.com/)' as a wrapper for a leaflet powered map that draws its points of interest from a geojson file. To get this up and running, do the following steps:

1\. Go to the [github repo for bootleaf](https://github.com/bmcbride/bootleaf).
2\. Fork a copy to a new repo (you have to be logged into github.com) by hitting the 'fork' button.
3\. In your copy of bootleaf, you now have a gh-pages version of the site. If you go to ```<yourusername>.github.io/bootleaf``` you should see an active version of the map.
4\. Now, the map is grabbing its data from a series of geojson files. You can use [the 'to geo json' service](http://togeojson.com/) to convert your csv to geojson. There are other services.
5\. Clone your repository in your desktop (by pressing the clone your repo in desktop).
6\. Open your desktop client, and make sure you're in the gh-pages branch
7\. Using your Windows explorer or Mac finder, put your newly created geojson file in the data folder.
8\. Commit and sync your changes.

9\. To add your data to the dropdown menu, you need to change the code in the index.html file:

```html
  <li class="dropdown">
                <a class="dropdown-toggle" id="downloadDrop" href="#" role="button" data-toggle="dropdown"><i class="fa fa-cloud-download white"></i>&nbsp;&nbsp;Download <b class="caret"></b></a>
                <ul class="dropdown-menu">
                  <li><a href="data/boroughs.geojson" download="boroughs.geojson" target="_blank" data-toggle="collapse" data-target=".navbar-collapse.in"><i class="fa fa-download"></i>&nbsp;&nbsp;Boroughs</a></li>
                  <li><a href="data/subways.geojson" download="subways.geojson" target="_blank" data-toggle="collapse" data-target=".navbar-collapse.in"><i class="fa fa-download"></i>&nbsp;&nbsp;Subway Lines</a></li>
                  <li><a href="data/DOITT_THEATER_01_13SEPT2010.geojson" download="theaters.geojson" target="_blank" data-toggle="collapse" data-target=".navbar-collapse.in"><i class="fa fa-download"></i>&nbsp;&nbsp;Theaters</a></li>
                  <li><a href="data/DOITT_MUSEUM_01_13SEPT2010.geojson" download="museums.geojson" target="_blank" data-toggle="collapse" data-target=".navbar-collapse.in"><i class="fa fa-download"></i>&nbsp;&nbsp;Museums</a></li>
                </ul>
```

And since you probably don't want that other stuff, you could delete it.

10\. You could change the 'about' pop-up here:

```html
<div class="tab-pane fade active in" id="about">
                <p>A simple, responsive template for building web mapping applications with <a href="http://getbootstrap.com/">Bootstrap 3</a>, <a href="http://leafletjs.com/" target="_blank">Leaflet</a>, and <a href="http://twitter.github.io/typeahead.js/" target="_blank">typeahead.js</a>. Open source, MIT licensed, and available on <a href="https://github.com/bmcbride/bootleaf" target="_blank">GitHub</a>.</p>
                <div class="panel panel-primary">
                  <div class="panel-heading">Features</div>
                  <ul class="list-group">
                    <li class="list-group-item">Fullscreen mobile-friendly map template with responsive navbar and modal placeholders</li>
                    <li class="list-group-item">jQuery loading of external GeoJSON files</li>
                    <li class="list-group-item">Logical multiple layer marker clustering via the <a href="https://github.com/Leaflet/Leaflet.markercluster" target="_blank">leaflet marker cluster plugin</a></li>
                    <li class="list-group-item">Elegant client-side multi-layer feature search with autocomplete using <a href="http://twitter.github.io/typeahead.js/" target="_blank">typeahead.js</a></li>
                    <li class="list-group-item">Responsive sidebar feature list synced with map bounds, which includes sorting and filtering via <a href="http://listjs.com/" target="_blank">list.js</a></li>
                    <li class="list-group-item">Marker icons included in grouped layer control via the <a href="https://github.com/ismyrnow/Leaflet.groupedlayercontrol" target="_blank">grouped layer control plugin</a></li>
                  </ul>
                </div>
```

11\. And you have to remove this:

```html
    <!-- Remove this maptiks analytics code from your BootLeaf implementation -->
    <script src="//cdn.maptiks.com/maptiks-leaflet.min.js"></script>
    <script>maptiks.trackcode='c7ca251e-9c17-47ef-ac33-e0fb24e05976';</script>
    <!-- End maptiks analytics code -->
```

Now the really hard part: putting your own base maps in. 

12\. To insert your own base map, you have to find, and modify, a file called app.js. You should be able to find it by following this path: bootleaf/assets/js/app.js

13\. You need to change these lines to point to your maps

```js
/* Basemap Layers */
var mapquestOSM = L.tileLayer("http://{s}.mqcdn.com/tiles/1.0.0/osm/{z}/{x}/{y}.png", {
  maxZoom: 19,
  subdomains: ["otile1", "otile2", "otile3", "otile4"],
  attribution: 'Tiles courtesy of <a href="http://www.mapquest.com/" target="_blank">MapQuest</a> <img src="http://developer.mapquest.com/content/osm/mq_logo.png">. Map data (c) <a href="http://www.openstreetmap.org/" target="_blank">OpenStreetMap</a> contributors, CC-BY-SA.'
});
var mapquestOAM = L.tileLayer("http://{s}.mqcdn.com/tiles/1.0.0/sat/{z}/{x}/{y}.jpg", {
  maxZoom: 18,
  subdomains: ["oatile1", "oatile2", "oatile3", "oatile4"],
  attribution: 'Tiles courtesy of <a href="http://www.mapquest.com/" target="_blank">MapQuest</a>. Portions Courtesy NASA/JPL-Caltech and U.S. Depart. of Agriculture, Farm Service Agency'
});
var mapquestHYB = L.layerGroup([L.tileLayer("http://{s}.mqcdn.com/tiles/1.0.0/sat/{z}/{x}/{y}.jpg", {
  maxZoom: 18,
  subdomains: ["oatile1", "oatile2", "oatile3", "oatile4"]
}), L.tileLayer("http://{s}.mqcdn.com/tiles/1.0.0/hyb/{z}/{x}/{y}.png", {
  maxZoom: 19,
  subdomains: ["oatile1", "oatile2", "oatile3", "oatile4"],
  attribution: 'Labels courtesy of <a href="http://www.mapquest.com/" target="_blank">MapQuest</a> <img src="http://developer.mapquest.com/content/osm/mq_logo.png">. Map data (c) <a href="http://www.openstreetmap.org/" target="_blank">OpenStreetMap</a> contributors, CC-BY-SA. Portions Courtesy NASA/JPL-Caltech and U.S. Depart. of Agriculture, Farm Service Agency'
})]);
```
...and then you'd have to go through the rest of that file and change up the .geojson pointers to point to your own data.

14\. Visit Github for a [template for mapping with leaflet](https://github.com/shawngraham/daea), drawing all of your point data and ancillary information from a csv file. Study the index.html file carefully to identify which lines you'd modify to change the base map, and to identify how elements in the csv are being rendered on the screen. [Visit this example that a former student made](https://xtina-r.github.io/daea/).

**Further reading:** Arian Katsimbras on making beautiful maps with [Tilemill](https://medium.com/@ArianKatsimbras/tilemill-c886a3ccba6a).
