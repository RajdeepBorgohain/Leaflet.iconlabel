#Leaflet.iconlabel
Adds support for displaying a label to the right of a Leaflet Icon.

##Using the plugin
If you are happy with the default icon and label styles, you should be able to use it without any modifications. To create a map marker with a label, declare your marker like:

````
var marker = new L.Marker(
	new L.LatLng(50.5, 30.51),
	{ icon: new L.Icon.Label.Default({ labelText: "A label" }) }
);
````

For a more complete example see [example/map-marker-iconlabels.html](https://github.com/jacobtoye/Leaflet.iconlabel/blob/master/example/map-marker-iconlabels.html)

###Using different icons
See ````L.Icon.Label.Default```` for comments on the positioning of the icon and label. If you wish to use a different sized icon or label you need to edit some of the options. 

E.g. Custom icon (24x24)

````
var SweetIcon = L.Icon.Label.extend({
	options: {
		iconUrl: 'images/icon.png',
		shadowUrl: null,
		iconSize: new L.Point(24, 24),
		iconAnchor: new L.Point(0, 1),
		labelAnchor: new L.Point(26, 0),
		wrapperAnchor: new L.Point(12, 13),
		labelClassName: 'sweet-deal-label'
	}
});
````

See [example/map-marker-iconlabels-custom.html](https://github.com/jacobtoye/Leaflet.iconlabel/blob/master/example/map-marker-iconlabels-custom.html) for complete example.

###Revealing labels
If you would like the labels to initially be hidden and only show on mouseover of the icon, use the L.Marker.Label and set the revealing = true in the marker options.

E.g.

````
var aMarker = new L.Marker.Label(
	[-37.7866, 175.2789],
	{ icon: new L.Icon.Label.Default({ labelText: "A label" }), revealing: true }
);
````