# Data Reconciliation and Augmentation

Reconciliation connects your dataset to external structured sources, enriching it with new information.

## Geocoding with Google Maps

You can use the Google Maps API to get latitude and longitude for addresses.

### Example:
```javascript
"http://maps.google.com/maps/api/geocode/json?sensor=false&address=" + escape(value, "url")
```

### Extract lat/lng:
```javascript
with(value.parseJson().results[0].geometry.location, pair, pair.lat + ", " + pair.lng)
```

## Splitting Coordinates

Once lat/lng string is created, you can split it into two columns:
- Column 1: Latitude
- Column 2: Longitude

## Map Creation

Use tools like [BatchGeo](http://batchgeo.com) to visualize coordinates.

## Reconciliation with Linked Data

Using RDFRefine (extension), you can match data to:
- DBpedia
- Wikidata
- Other linked open datasets

Steps:
1. Column menu → Reconcile → Start reconciling
2. Choose reconciliation service
3. Match entities and retrieve metadata

### Example

Use the “University” column to match with DBpedia:
- Add new columns like founding year, location, entity type

## Custom Reconciliation Services

You can create your own service to match custom datasets or APIs.