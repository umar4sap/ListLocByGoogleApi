

# ListLocByGoogleApi
In this application user can pick the location from address list and the same will be display in map


# Hitting Google API


API link
<pre><script src="https://maps.googleapis.com/maps/api/js?v=3.exp&sensor=false"></script></pre>



#Default Map Location

Create a Google coordinate object for where to initially center the map


var latlng = new google.maps.LatLng( 38.8951, -77.0367 );

#Map

Show the Google map in the div with the attribute id 'map-canvas'.

map = new google.maps.Map(document.getElementById('map-canvas'), mapOptions);



#geocoder

Update the Google map for the user's Listed address
	function UpdateMap( )
	{

	 // instantiate a geocoder object
	}
		var geocoder = new google.maps.Geocoder();

Make asynchronous call to Google geocoding APi
		geocoder.geocode( { 'address': address }, function(results, status){}

#showLocation API
Show the location (address) on the map

		function ShowLocation( latlng, address, addr_type )




#address type

switch ( addr_type )
        		{
        		// user specified a state

        		case "administrative_area_level_1"	: zoom = 6; break;

        			// user specified a city/town

        		case "locality"						: zoom = 10; break;
        			// user specified a street address

        		case "street_address"				: zoom = 15; break;

        		}



#Marker


Place a Google Marker at the same location as the map center 
 
 
new google.maps.Marker

e.g
var marker = new google.maps.Marker( {
			position: latlng,
			map: map,
			title: address
		});


#InfoWindow

HTML text to display in the InfoWindow

new google.maps.InfoWindow

E.g
var infowindow = new google.maps.InfoWindow( {
 content: contentString
 } );




#addListener
Set event to display the InfoWindow anchored to the marker when the marker is clicked
E.g

google.maps.event.addListener(
marker, 'click', function() {
 infowindow.open( map, marker );
 });

 #DOMListner
 
Call the method 'Init()' to display the google map when the web page is displayed ( load event )

 google.maps.event.addDomListener( window, 'load', Init );
