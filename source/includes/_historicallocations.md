<script type="text/javascript" src="../javascripts/sensorup.js"></script>
<link rel="stylesheet" type="text/css" href="../stylesheets/sensorup.css">

# HistoricalLocations

## addNewHistoricalLocation

```csharp
Service service = new Service ("http://example.org/OGCSensorThings/v1.0");
string response = service.addNewThing ("thermostate of the home office", "",62864);

Console.Out.WriteLine(response);

```

><button id="btn" onclick="show('#hlocExample1')">Show Response</button><div id="hlocExample1" class="exampleStyle" style="display: none;">
{<br><span class="textIndent">
  "@iot.selfLink": "http://example.org/OGCSensorThings/v1.0/Locations(27835)",<br>
  "@iot.id": 27835,<br>
  "encodingType": "application/vnd.geo+json",<br>
  "Things@iot.navigationLink": "../Locations(27835)/Things",<br>
  "description": "my backyard",<br>
  "location": {<br><span class="textIndent">
    "coordinates": [
      -117.123,
      54.123
    ],<br>
    "type": "Point"<br></span>
  },<br>
  "HistoricalLocations@iot.navigationLink": "../Locations(27835)/HistoricalLocations"<br></span>
}</div>

Create new HistoricalLocation entity in OGC SensorThings database.

**Parameters**

*description:* A description of the HistoricalLocation.

*properties:* The properties of the HistoricalLocation.

*locationID:* The id of the HistoricalLocation to be associated with the new HistoricalLocation entity.

**Returns**

JSON string of the new HistoricalLocation entity or error message if new record is not added.


Parameters | Type | Required
-------------- | -------------- | --------------
description | string | mandatory
properties | string | optional
locationID | long | optional


## addNewHistoricalLocationByJSON

```csharp
Service service = new Service ("http://example.org/OGCSensorThings/v1.0");

string jsonString = "{
      \"time\": \"2015-09-20T23:22:51.857Z\",
      \"Thing\":{\"@iot.id\": 97494}, 
      \"Locations\":[{\"@iot.id\": 114148}]
    }";

string value = service.addNewHistoricalLocationByJSON (jsonString);
Console.Out.WriteLine(response);

```
><button id="btn" onclick="show('#hlocExample2')">Show Response</button><div id="hlocExample2" class="exampleStyle" style="display: none;">
{<span class="textIndent"><br>
  "@iot.selfLink":"http://example.org/OGCSensorThings/v1.0/HistoricalLocations(114366)",<br>
  "Thing@iot.navigationLink":"../HistoricalLocations(114366)/Thing",<br>
  "@iot.id":114366,<br>
  "time":"2015-09-20T23:22:51.857Z",<br>
  "Locations@iot.navigationLink":"../HistoricalLocations(114366)/Locations"</span><br>
}</div>

Create new HistoricalLocation entity in OGC SensorThings database.

**Parameters**

*jsonString:* A JSON string describing the new HistoricalLocation entity to be created.

**Returns**

JSON string of the new HistoricalLocation entity or Error message if new record is not added.


Parameters | Type | Required
-------------- | -------------- | --------------
jsonString | string | mandatory


## deleteHistoricalLocation

```csharp
Service service = new Service ("http://example.org/OGCSensorThings/v1.0");
string response = service.deleteHistoricalLocation (114147);

Console.Out.WriteLine(response);
```
><button id="btn" onclick="show('#hlocExample3')">Show Response</button><div id="hlocExample3" class="exampleStyle" style="display: none;">
Succeeded: Record is deleted</div>

Delete HistoricalLocation entity from the OGC SensorThings database.

**Parameters**

*id:* The id of the HistoricalLocation entity to be deleted.

**Returns**

String showing the status of the delete operation.

Parameters | Type | Required
-------------- | -------------- | --------------
id | long | mandatory




## getHistoricalLocations

```csharp

Service service = new Service("http://example.org/OGCSensorThings/v1.0");
ArrayList array = service.getHistoricalLocations(0, 2)		//return the first two elements

foreach(HistoricalLocation item in array){
	//print the properties
	Console.out.WriteLine("ID: "+item.id);
	Console.out.WriteLine("Time: "+item.time);
}

```
><button id="btn" onclick="show('#hlocExample4')">Show Response</button><div id="hlocExample4" class="exampleStyle" style="display: none;">
ID: 113846<br>
Time: 2015-09-20T22:29:53.483Z<br>
ID: 97487<br>
Time: 2015-09-18T23:35:12.212Z<br>
</div>

Returns an ArrayList of HistoricalLocation objects according to the specified skip and top values.

**Parameters**

*skip:* Indicate the number of records to be skiped from the begining of the returned list from the server.

*top:* Indicate the maximum number of records to be returned.

**Returns**

An ArrayList of HistoricalLocation objects

Parameters | Type | Required
-------------- | -------------- | --------------
skip | int | mandatory
top | int | mandatory


## getHistoricalLocationsJSON

```csharp

Service service = new Service("http://example.org/OGCSensorThings/v1.0");
string json = service.getHistoricalLocationsJSON(0, 2,"","id,time","","id",false);		//skip the first three elements and return 10 elements only displaying id, select id's that are greater than 10000, order by id, and don't return the count. 

//print the json string to console
Console.out.WriteLine(json);

```
><button id="btn" onclick="show('#hlocExample5')">Show Response</button><div id="hlocExample5" class="exampleStyle" style="display: none;">
{<span class="textIndent"><br>
  "@iot.nextLink":"http://example.org/OGCSensorThings/v1.0/HistoricalLocations?$skip=2&$top=2&$expand=&$filter=&$orderby=id&$count=False&$select=id,time",<br>
  "value":[<br>
    {<span class="textIndent">
      "id":10,"time":"2015-08-17T20:55:48.967Z"</span><br>
    },{<span class="textIndent">
      "id":20,"time":"2015-08-17T20:55:54.797Z"</span><br>
    }]</span><br>
}</div>

Returns a JSON string of HistoricalLocations records according to the specified skip, top, expand, select, filter, orderby, and count values.

**Parameters**

*skip:* Indicate the number of records to be skiped from the begining of the returned list from the server.

*top:* Indicate the maximum number of records to be returned.

*expand:* Indicates the related entities to be represented inline. Its value is a comma seperated list of navigation property names (e.g. "parameter1, parameter2").

*select:* Indicates which propeties to be returned explicitly. Its value is a comma seperated list of navigation property names (e.g. "parameter1, parameter2")

*filter:* Allows clients to filter a collection of entities that are addressed by a request URL.

*orderby:* Specifies the order in which items are returned from the service. Its value is a comma seperated list of navigation property names (e.g. "parameter1, parameter2")

*count:* A boolean value that specifies whether the total count of items be returned along with the result or not.

**Returns**

A JSON string of the requested HistoricalLocations records.

Parameters | Type | Required
-------------- | -------------- | --------------
skip | int | mandatory
top | int | mandatory
expand | string | mandatory
filter | string | mandatory
orderby | string | mandatory
count | boolean | mandatory

## getHistoricalLocationById

```csharp

Service service = new Service("http://example.org/OGCSensorThings/v1.0");
HistoricalLocation hisloc = service.getHistoricalLocationById(display); 

//print to console the properties of location
Console.out.WriteLine("ID: "+hisloc.id);
Console.out.WriteLine("time: "+hisloc.time);
Console.out.WriteLine("location: ["+i.location.coordinates.ToArray()[0]+", "+i.location.coordinates.ToArray()[1]+"]");

```
><button id="btn" onclick="show('#hlocExample6')">Show Response</button><div id="hlocExample6" class="exampleStyle" style="display: none;">
ID: 74891<br>
time: 2015-09-16 1:18:58 PM<br>
location: [0.63808, 0.00476]<br>
</div>

Returns a HistoricalLocation object of the given id parameter.

**Parameters**

*id:* The id of the requested HistoricalLocation entity.

**Returns**

A HistoricalLocation object

Parameters | Type | Required
-------------- | -------------- | --------------
id | long | mandatory


## getHistoricalLocationByIdJSON

```csharp

Service service = new Service("http://example.org/OGCSensorThings/v1.0");
string json = service.getHistoricalLocationByIdJSON(74891); 

//print to JSON string to console
Console.out.WriteLine(json);

```
><button id="btn" onclick="show('#hlocExample7')">Show Response</button><div id="hlocExample7" class="exampleStyle" style="display: none;">
{<span class="textIndent"><br>
  "@iot.selfLink": "http://example.org/OGCSensorThings/v1.0/HistoricalLocations(74891)",<br>
  "Thing@iot.navigationLink": "../HistoricalLocations(74891)/Thing",<br>
  "@iot.id": 74891,<br>
  "time": "2015-09-16T13:18:58.726Z",<br>
  "Locations@iot.navigationLink": "../HistoricalLocations(74891)/Locations"</span><br>
}</div>

Returns a JSON string of the HistoricalLocation record by the given id parameter.

**Parameters**

*id:* The id of the requested HistoricalLocation entity.

**Returns**

A JSON string of the requested HistoricalLocation entity

Parameters | Type | Required
-------------- | -------------- | --------------
id | long | mandatory
