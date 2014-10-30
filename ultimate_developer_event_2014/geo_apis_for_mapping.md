## Geo apis for mapping and more

### Raj Singh

__Summary:__
In this session we'll walk through all the basic steps of building geo-enabled apps, from capturing a device's location, to storing that data in a cloud database-as-a-service, to mapping and visualization on the other end. We'll learn the HTML5 Geolocation API, which gives web developers an API for accessing the GPS (or other positioning hardware) of a device. Then we'll use the Cloudant database-as-a-service for cloud storage and play around with some geo-enabled search APIs used by Cloudant, Yelp, Facebook and others. Finally, we'll put our data on a map and see how data accessed from various APIs can come together in a single map interface.

---

https://github.com/rajrsingh/locationtracker

Agenda:

1. HTML5 Geolocation API
2. Replication (insert to DB)
3. Geo Query
4. Mapping 

W3Cs Geolocation Working Group APIs

DeviceOrientation

* compass heading
* accelleration

Geolocation

* x, y, altitude
* once, or continuous

Interfaces

* void getCurrentPosition()
* long watchPosition()
* void clearWatch()

Can save locally to PouchDB, which will sync with CouchDB later when there's a connection

Geo Search (Lucene / Solr - spatial api)

* only for pOINT data
* search geo-coordinates by indexing longitude and latitude fields
	* bounding box
	* radius
	
Mapping with Leaflet.js

Takeaways

* Cloudant or CouchDB - Javascript & JSON everywhere from front-end to database
* GeoJSON is a great standard for Javascript-centric apps
* Demos are easy, managing millions of locations is tougher
	* requires really good indexing
	* lightweight mapping apps need to catch up
	
