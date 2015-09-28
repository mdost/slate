<script type="text/javascript" src="../javascripts/sensorup.js"></script>
<link rel="stylesheet" type="text/css" href="../stylesheets/sensorup.css">

# Locations

## addNewLocation

```csharp

Service service = new Service ("http://example.org/OGCSensorThings/v1.0");

ArrayList location = new ArrayList ();
location.Add (52.244344);
location.Add (-114.232443);

string response = service.addNewLocation ("application/vnd.geo+json","Android phone","Point",location,97494);

Console.Out.WriteLine(response);

```

><button id="btn" onclick="show('#locExample1')">Show Response</button><div id="locExample1" class="exampleStyle" style="display: none;">
{<span class="textIndent"><br>
  "@iot.selfLink":"http://example.org/OGCSensorThings/v1.0/Locations(114148)",<br>
  "@iot.id":114148,<br>
  "encodingType":"application/vnd.geo+json",<br>
  "Things@iot.navigationLink":"../Locations(114148)/Things",<br>
  "description":"Android phone",<br>
  "location":{<span class="textIndent">
      "coordinates":[52.244344,-114.232443],<br>
      "type":"Point"</span><br>
    },<br>
  "HistoricalLocations@iot.navigationLink":"../Locations(114148)/HistoricalLocations"</span><br>
}</div>

Create new Location entity in OGC SensorThings database.

**Parameters**

*description:* A description of the Location.

*properties:* The properties of the Location.

*locationID:* The id of the Location to be associated with the new Location entity.

**Returns**

JSON string of the new Location entity or error message if new record is not added.


Parameters | Type | Required
-------------- | -------------- | --------------
description | string | mandatory
properties | string | optional
locationID | long | optional


## addNewLocationByJSON

```csharp
Service service = new Service ("http://example.org/OGCSensorThings/v1.0");
string jsonString = "{
    \"location\": {        
        \"coordinates\": [52.244344, -114.232443],
        \"type\": \"Point\"
      },
      \"description\": \"Android phone\",
      \"encodingType\": \"application/vnd.geo+json\"
    }";

string response = service.addNewLocationByJSON(jsonString);

Console.Out.WriteLine(response);

```

><button id="btn" onclick="show('#locExample2')">Show Response</button><div id="locExample2" class="exampleStyle" style="display: none;">
{<span class="textIndent"><br>
  "@iot.selfLink":"http://example.org/OGCSensorThings/v1.0/Locations(114148)",<br>
  "@iot.id":114148,<br>
  "encodingType":"application/vnd.geo+json",<br>
  "Things@iot.navigationLink":"../Locations(114148)/Things",<br>
  "description":"Android phone",<br>
  "location":{<span class="textIndent">
      "coordinates":[52.244344,-114.232443],<br>
      "type":"Point"</span><br>
    },<br>
  "HistoricalLocations@iot.navigationLink":"../Locations(114148)/HistoricalLocations"</span><br>
}</div>

Create new Location entity in OGC SensorThings database.

**Parameters**

*jsonString:* A JSON string describing the new Location entity to be created.

**Returns**

JSON string of the new Location entity or error message if new record is not added.


Parameters | Type | Required
-------------- | -------------- | --------------
jsonString | string | mandatory


## deleteLocation

```csharp
Service service = new Service ("http://example.org/OGCSensorThings/v1.0");
string response = service.deleteLocation(114173);
Console.Out.WriteLine(response);

```
><button id="btn" onclick="show('#locExample3')">Show Response</button><div id="locExample3" class="exampleStyle" style="display: none;">
Succeeded: Record is deleted</div>

Delete Location entity from the OGC SensorThings database.

**Parameters**

*id:* The id of the Location entity to be deleted.

**Returns**

String showing the status of the delete operation.

Parameters | Type | Required
-------------- | -------------- | --------------
id | long | mandatory




## getLocations

```csharp

Service service = new Service("http://example.org/OGCSensorThings/v1.0");
ArrayList array = service.getLocations(3, 2)		//Skip the first three elements, return the next two elements.

foreach(Location item in array){
	//print the properties
  Console.out.WriteLine('ID: '+item.id);
  Console.out.WriteLine('description: '+item.description);
  Console.out.WriteLine('encodingType: '+item.encodingType);
}

```

><button id="btn" onclick="show('#locExample4')">Show Response</button><div id="locExample4" class="exampleStyle" style="display: none;">
ID: 114173<br>
encodingType: application/vnd.geo+json<br>
description: Android phone<br>
ID: 114148<br>
encodingType: application/vnd.geo+json<br>
description: BGS<br>
</div>

Returns an ArrayList of Location objects according to the specified skip and top values.

**Parameters**

*skip:* Indicate the number of records to be skiped from the begining of the returned list from the server.

*top:* Indicate the maximum number of records to be returned.

**Returns**

An ArrayList of Location objects

Parameters | Type | Required
-------------- | -------------- | --------------
skip | int | mandatory
top | int | mandatory


## getLocationsJSON

```csharp

Service service = new Service("http://example.org/OGCSensorThings/v1.0");
string json = service.getLocationsJSON(2, 2, "", "description", "", "id", true);		//skip the first two elements and return two elements only displaying the description, order by id, and return the count as well. 

//print the json string to console
Console.out.WriteLine(json);

```
><button id="btn" onclick="show('#locExample5')">Show Response</button><div id="locExample5" class="exampleStyle" style="display: none;">
{<span class="textIndent"><br>
  "@iot.nextLink":"http://example.org/OGCSensorThings/v1.0/Locations?$skip=4&$top=2&$expand=&$filter=&$orderby=id&$count=True&$select=description",<br>
  "count":616,<br>
  "value":[<br>
    {<span class="textIndent">
      "description":"West Roof"</span><br>
    },{<span class="textIndent">
      "description":"West Roof"</span><br>
    }]</span><br>
}</div>

Returns a JSON string of Location records according to the specified skip, top, expand, select, filter, orderby, and count values.

**Parameters**

*skip:* Indicate the number of records to be skiped from the begining of the returned list from the server.

*top:* Indicate the maximum number of records to be returned.

*expand:* Indicates the related entities to be represented inline. Its value is a comma seperated list of navigation property names (e.g. "parameter1, parameter2").

*select:* Indicates which propeties to be returned explicitly. Its value is a comma seperated list of navigation property names (e.g. "parameter1, parameter2")

*filter:* Allows clients to filter a collection of entities that are addressed by a request URL.

*orderby:* Specifies the order in which items are returned from the service. Its value is a comma seperated list of navigation property names (e.g. "parameter1, parameter2")

*count:* A boolean value that specifies whether the total count of items be returned along with the result or not.

**Returns**

A JSON string of the requested Location records.

Parameters | Type | Required
-------------- | -------------- | --------------
skip | int | mandatory
top | int | mandatory
expand | string | mandatory
filter | string | mandatory
orderby | string | mandatory
count | boolean | mandatory

## getLocationById

```csharp

Service service = new Service("http://example.org/OGCSensorThings/v1.0");
Location loc = service.getLocationById(114148); 

//print to console the properties of location
Console.out.WriteLine('ID: '+loc.id);
Console.out.WriteLine('description: '+loc.description);
Console.out.WriteLine('encodingType: '+loc.encodingType);
Console.out.WriteLine('['+loc.toArray()[0]+',  '+loc.toArray()[1]+']');
Console.out.WriteLine('type: '+loc.locationType);

```
><button id="btn" onclick="show('#locExample6')">Show Response</button><div id="locExample6" class="exampleStyle" style="display: none;">
ID: 114148<br>
description: BGS<br>
encodingType: application/vnd.geo+json<br>
coordinates: [0.63808, 0.00476]<br>
type: Point</div>

Returns a Location object of the given id parameter.

**Parameters**

*id:* The id of the requested Location entity.

**Returns**

A Location object

Parameters | Type | Required
-------------- | -------------- | --------------
id | long | mandatory


## getLocationByIdJSON

```csharp

Service service = new Service("http://example.org/OGCSensorThings/v1.0");
string json = service.getLocationByIdJSON(74883); 

//print to JSON string to console
Console.out.WriteLine(json);

```
><button id="btn" onclick="show('#locExample7')">Show Response</button><div id="locExample7" class="exampleStyle" style="display: none;">
{<span class="textIndent"><br>
  "@iot.selfLink": "http://example.org/OGCSensorThings/v1.0/Locations(74890)",<br>
  "@iot.id": 74890,<br>
  "encodingType": "application/vnd.geo+json",<br>
  "Things@iot.navigationLink": "../Locations(74890)/Things",<br>
  "description": "BGS",<br>
  "location": {<span class="textIndent">
    "coordinates": [0.63808,0.00476],<br>
    "type": "Point"</span><br>
  },<br>
  "HistoricalLocations@iot.navigationLink": "../Locations(74890)/HistoricalLocations"</span><br>
}</div>

Returns a JSON string of the Location record by the given id parameter.

**Parameters**

*id:* The id of the requested Location entity.

**Returns**

A JSON string of the requested Location entity

Parameters | Type | Required
-------------- | -------------- | --------------
id | long | mandatory
