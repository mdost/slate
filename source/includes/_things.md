<script type="text/javascript" src="../javascripts/sensorup.js"></script>
<link rel="stylesheet" type="text/css" href="../stylesheets/sensorup.css">

# Things

## addNewThing

```csharp

Service service = new Service ("http://example.org/OGCSensorThings/v1.0");
string response = service.addNewThing ("thermostate of the home office", "",62864);

Console.Out.WriteLine(response);

```

><button id="btn" onclick="show('#thingExample1')">Show Response</button><div id="thingExample1" class="exampleStyle" style="display: none;">
{<span class="textIndent"><br>
	"@iot.selfLink":"http://example.org/OGCSensorThings/v1.0/Things(97339)",<br>
	"Datastreams@iot.navigationLink":"../Things(97339)/Datastreams",<br>
	"@iot.id":97339,<br>
	"description":"thermostate of the home office",<br>
	"Locations@iot.navigationLink":"../Things(97339)/Locations",<br>
	"properties":{},<br>
	"HistoricalLocations@iot.navigationLink":"../Things(97339)/HistoricalLocations"</span><br>
}</div>

Create new Thing entity in OGC SensorThings database.

**Parameters**

*description:* A description of the Thing.

*properties:* The properties of the Thing.

*locationID:* The id of the Location to be associated with the new Thing entity.

**Returns**

JSON string of the new Thing entity or Error message if new record is not added.


Parameters | Type | Required
-------------- | -------------- | --------------
description | string | mandatory
properties | string | optional
locationID | long | mandatory


## addNewThingByJSON

```csharp

Service service = new Service ("http://example.org/OGCSensorThings/v1.0");
string jsonString="{
		\"description\": \"thermostate of the home office\", 
		\"properties\": {\"color:\": \"green\"}, 
		\"Locations\":[{\"@iot.id\":  53416 }]}
	}";

string response = service.addNewThingByJSON (jsonString);

Console.Out.WriteLine(response);

```

><button id="btn" onclick="show('#thingExample2')">Show Output</button><div id="thingExample2" class="exampleStyle" style="display: none;">
{<span class="textIndent"><br>
	"@iot.selfLink":"http://example.org/OGCSensorThings/v1.0/Things(97494)",<br>
	"Datastreams@iot.navigationLink":"../Things(97494)/Datastreams",<br>
	"@iot.id":97494,<br>
	"description":"thermostate of the home office",<br>
	"Locations@iot.navigationLink":"../Things(97494)/Locations",<br>
	"properties":{<span class="textIndent">
		"color:":"green"<br></span>
	},<br>
	"HistoricalLocations@iot.navigationLink":"../Things(97494)/HistoricalLocations"</span><br>
}</div>

Create New Thing entity in OGC SensorThings database.

**Parameters**

*jsonString:* A JSON string describing the new Thing entity to be created.

**Returns**

JSON string of the new Thing entity or Error message if new record is not added.


Parameters | Type | Required
-------------- | -------------- | --------------
jsonString | string | mandatory


## deleteThing

```csharp

Service service = new Service ("http://example.org/OGCSensorThings/v1.0");
string response = service.deleteThing (62674);

Console.Out.WriteLine(response);

```

><button id="btn" onclick="show('#thingExample3')">Show Response</button><div id="thingExample3" class="exampleStyle" style="display: none;">
Succeeded: Record is deleted</div>

Delete Thing entity from the OGC SensorThings database.

**Parameters**

*id:* The id of the Thing entity to be deleted.

**Returns**

String showing the status of the delete operation.

Parameters | Type | Required
-------------- | -------------- | --------------
id | long | mandatory


## setThingDescription

```csharp

Service service = new Service ("http://example.org/OGCSensorThings/v1.0");
string response = service.setThingDescription (97494, "The thermostate of the building.");

Console.Out.WriteLine(response);

```
><button id="btn" onclick="show('#thingExample4')">Show Response</button><div id="thingExample4" class="exampleStyle" style="display: none;">
{<span class="textIndent"><br>
	"@iot.selfLink":"http://example.org/OGCSensorThings/v1.0/Things(97494)",<br>
	"Datastreams@iot.navigationLink":"../Things(97494)/Datastreams",<br>
	"@iot.id":97494,<br>
	"description":"The thermostate of the building.",<br>
	"Locations@iot.navigationLink":"../Things(97494)/Locations",<br>
	"properties":{<span class="textIndent">
		"color:":"green"<br></span>
	},<br>
	"HistoricalLocations@iot.navigationLink":"../Things(97494)/HistoricalLocations"</span>
}</div>


Update the Description of a Thing entity.

**Parameters**

*id:* The id of the Thing entity to be updated.

*description:* The new description of the Thing entity.

**Returns**

String showing the updated status of the operation.

Parameters | Type | Required
-------------- | -------------- | --------------
id | long | mandatory
description | string | mandatory


## setThingProperties

```csharp

Service service = new Service ("http://example.org/OGCSensorThings/v1.0");
string response = service.setThingProperties (97494, "\"material\": \"plastic\"");

Console.Out.WriteLine(response);

```

><button id="btn" onclick="show('#thingExample5')">Show Response</button><div id="thingExample5" class="exampleStyle" style="display: none;">
{<span class="textIndent"><br>
	"@iot.selfLink":"http://example.org/OGCSensorThings/v1.0/Things(97494)",<br>
	"Datastreams@iot.navigationLink":"../Things(97494)/Datastreams",<br>
	"@iot.id":97494,<br>
	"description":"The thermostate of the building.",<br>
	"Locations@iot.navigationLink":"../Things(97494)/Locations",<br>
	"properties":{<span class="textIndent">
		"material":"plastic"<br></span><br>
	},<br>
	"HistoricalLocations@iot.navigationLink":"../Things(97494)/HistoricalLocations"</span><br>
}</div>

Update the Properties of a Thing entity.

**Parameters**

*id:* The id of the Thing entity to be updated.

*properties:* The new properties of the Thing entity.

**Returns**

String showing the updated status of the operation.

Parameters | Type | Required
-------------- | -------------- | --------------
id | long | mandatory
properties | string | mandatory


## setThingLocation

```csharp

Service service = new Service ("http://example.org/OGCSensorThings/v1.0");
string response = service.setThingLocation (97494, 74890);

Console.Out.WriteLine(response);

```

><button id="btn" onclick="show('#thingExample6')">Show Response</button><div id="thingExample6" class="exampleStyle" style="display: none;">
{<span class="textIndent"><br>
	"@iot.selfLink":"http://example.org/OGCSensorThings/v1.0/Things(97494)",<br>
	"Datastreams@iot.navigationLink":"../Things(97494)/Datastreams",<br>
	"@iot.id":97494,<br>
	"description":"The thermostate of the building.",<br>
	"Locations@iot.navigationLink":"../Things(97494)/Locations",<br>
	"properties":{<span class="textIndent">
		"material":"plastic"<br></span>
	},<br>
	"HistoricalLocations@iot.navigationLink":"../Things(97494)/HistoricalLocations"<br>
}</div>

Update the Properties of a Thing entity.

**Parameters**

*id:* The id of the Thing entity to be updated.

*locationID:* The id of the new Location to be associated with the Thing entity.

**Returns**

String showing the updated status of the operation.

Parameters | Type | Required
-------------- | -------------- | --------------
id | long | mandatory
locationID | long | mandatory


## getThings

```csharp

Service service = new Service("http://example.org/OGCSensorThings/v1.0");
ArrayList things = service.getThings(1, 2)		//skip first element and return the next elements

foreach(Thing item in things){
	//print the properties
	Console.out.WriteLine(item.id);
	Console.out.WriteLine(item.description);
	Console.out.WriteLine(item.properties);
}

```

><button id="btn" onclick="show('#thingExample7')">Show Response</button><div id="thingExample7" class="exampleStyle" style="display: none;">
ID: 97486<br>
description: thermostate of the home office<br>
properties: { "color": "green" }<br>
ID: 97365<br>
description: thermostate of the home office<br>
properties: { "color:": "green" }</div>

Returns an ArrayList of Thing objects according to the specified skip and top values.

**Parameters**

*skip:* Indicate the number of records to be skiped from the begining of the returned list from the server.

*top:* Indicate the maximum number of records to be returned.

**Returns**

An ArrayList of Thing objects

Parameters | Type | Required
-------------- | -------------- | --------------
skip | int | mandatory
top | int | mandatory


## getThingsJSON

```csharp

Service service = new Service("http://example.org/OGCSensorThings/v1.0");
string json = service.getThingsJSON(3, 2, "","id, description","id gt 10000","id",true);		//skip the first three elements and return 10 elements only displaying id and description, select id's that are greater than 10000, order by id, and return the count as well. 

//print the json string to console
Console.out.WriteLine(json);

```
><button id="btn" onclick="show('#thingExample8')">Show Response</button><div id="thingExample8" class="exampleStyle" style="display: none;">
{<span class="textIndent"><br>
	"@iot.nextLink":"http://example.org/OGCSensorThings/v1.0/Things?$skip=5&$top=2&$expand=&$filter=id gt 10000&$orderby=id&$count=True&$select=id,description",<br>
	"count":690,<br>
	"value":[{<span class="textIndent">
			"id":14038<br>
			"description": "CYKD-AKLAVIK AIRPORT test1"<br></span>
		},{<span class="textIndent">
			"id":14039<br>
			"description": "Google nexus 5"<br></span>
	}]</span><br>
}</div>

Returns a JSON string of Thing records according to the specified skip, top, expand, select, filter, orderby, and count values.

**Parameters**

*skip:* Indicate the number of records to be skiped from the begining of the returned list from the server.

*top:* Indicate the maximum number of records to be returned.

*expand:* Indicates the related entities to be represented inline. Its value is a comma seperated list of navigation property names (e.g. "parameter1, parameter2").

*select:* Indicates which propeties to be returned explicitly. Its value is a comma seperated list of navigation property names (e.g. "parameter1, parameter2")

*filter:* Allows clients to filter a collection of entities that are addressed by a request URL.

*orderby:* Specifies the order in which items are returned from the service. Its value is a comma seperated list of navigation property names (e.g. "parameter1, parameter2")

*count:* A boolean value that specifies whether the total count of items be returned along with the result or not.

**Returns**

A JSON string of the requested Thing records.

Parameters | Type | Required
-------------- | -------------- | --------------
skip | int | mandatory
top | int | mandatory
expand | string | mandatory
filter | string | mandatory
orderby | string | mandatory
count | boolean | mandatory

## getThingById

```csharp

Service service = new Service("http://example.org/OGCSensorThings/v1.0");
Thing thing = service.getThingById(74883); 

//print to console the properties of thing
Console.out.WriteLine(thing.id);
Console.out.WriteLine(thing.description);
Console.out.WriteLine(thing.properties);

```

><button id="btn" onclick="show('#thingExample9')">Show Response</button><div id="thingExample9" class="exampleStyle" style="display: none;">
ID: 74883<br>
description: The thermostate of the office<br>
properties: {}</div>

Returns a Thing object of the given id parameter.

**Parameters**

*id:* The id of the requested Thing entity.

**Returns**

A Thing object

Parameters | Type | Required
-------------- | -------------- | --------------
id | long | mandatory


## getThingByIdJSON

```csharp

Service service = new Service("http://example.org/OGCSensorThings/v1.0");
string json = service.getThingByIdJSON(74883); 

//print to JSON string to console
Console.out.WriteLine(json);

```

><button id="btn" onclick="show('#thingExample10')">Show Response</button><div id="thingExample10" class="exampleStyle" style="display: none;">
{<span class="textIndent"><br>
  "@iot.selfLink": "http://example.org/OGCSensorThings/v1.0/Things(74883)",<br>
  "Datastreams@iot.navigationLink": "../Things(74883)/Datastreams",<br>
  "@iot.id": 74883,<br>
  "description": "Thermostate of the office",<br>
  "Locations@iot.navigationLink": "../Things(74883)/Locations",<br>
  "properties": {},<br>
  "HistoricalLocations@iot.navigationLink": "../Things(74883)/HistoricalLocations"</span>
}</div>

Returns a JSON string of the Thing record by the given id parameter.

**Parameters**

*id:* The id of the requested Thing entity.

**Returns**

A JSON string of the requested Thing entity

Parameters | Type | Required
-------------- | -------------- | --------------
id | long | mandatory
