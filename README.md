query-overpass [![NPM version](https://badge.fury.io/js/query-overpass)](http://badge.fury.io/js/query-overpass)
=========

Make queries to [OpenStreetMap](http://www.openstreetmap.org/)'s [overpass API](http://wiki.openstreetmap.org/wiki/Overpass_API) and output as [GeoJSON](http://geojson.org/).

## cli

install:

    $ npm install -g query-overpass

use:

    $ echo '[out:json];node(57.7,11.9,57.8,12.0)[amenity=bar];out;' | query-overpass

Optionally, a file containing the query can be passed as the first argument:

    $ query-overpass query.ql

## usage

Installation is easy with npm:

    npm install query-overpass

## api

query-overpass exports a single function:

### query_overpass(query, callback)

Performs the provided query and calls the callback when done. The callback is of the form

    callback(error, data)

Where error is an object containing `message` and `statusCode` if an error occured, or `undefined` if
no error occured. `data` will be the query response as an GeoJSON object.
