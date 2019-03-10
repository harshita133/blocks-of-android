# Google Places API
The Places API is a service that returns information about places using HTTP requests. Places are defined within this API as establishments, geographic locations, or prominent points of interest.

## Introducing the API

The following place requests are available:
* **Place Search** - returns a list of places based on a user's location or search string.
* **Place Details** - returns more detailed information about a specific place, including user reviews.
* **Place Photos** - provides access to the millions of place-related photos stored in Google's Place database.
* **Place Autocomplete** - automatically fills in the name and/or address of a place as users type.
* **Query Autocomplete** - provides a query prediction service for text-based geographic searches, returning suggested queries as users type.

Each of the services is accessed as an HTTP request, and returns either an JSON or XML response. All requests to a Places service must use the https:// protocol, and include an API key.

## Place Search
The Places API allows you to query for place information on a variety of categories, such as: establishments, prominent points of interest, geographic locations, and more. You can search for places either by proximity or a text string. A Place Search returns a list of places along with summary information about each place; additional information is available via a Place Details query.

### Nearby Search requests:
A Nearby Search lets you search for places within a specified area. You can refine your search request by supplying keywords or specifying the type of place you are searching for.
A Nearby Search request is an HTTP URL of the following form:
https://maps.googleapis.com/maps/api/place/nearbysearch/output?parameters
where output may be either of the following values:
* **json** (recommended) indicates output in JavaScript Object Notation (JSON)
* **xml** indicates output as XML

Certain parameters are required to initiate a Nearby Search request. As is standard in URLs, all parameters are separated using the ampersand (&) character.

**Required parameters**
* **key** — Your application's API key. This key identifies your application. 
* **location** — The latitude/longitude around which to retrieve place information. This must be specified as latitude,longitude.
* **radius** — Defines the distance (in meters) within which to return place results. The maximum allowed radius is 50 000 meters. Note that radius must not be included if rankby=distance  is specified. If rankby=distance is specified, then one or more of keyword, name, or type is required.

## Nearby search example
The following example is a search request for places of type 'restaurant' within a 1500m radius of a point in New Delhi.

https://maps.googleapis.com/maps/api/place/nearbysearch/json?location=28.7041,77.1025&radius=1500&type=restaurant&key=YOUR_API_KEY

Note: In this example, you need to replace the key with your own API key in order for the request to work in your application.
