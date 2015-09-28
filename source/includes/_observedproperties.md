<script type="text/javascript" src="../javascripts/sensorup.js"></script>
<link rel="stylesheet" type="text/css" href="../stylesheets/sensorup.css">

# ObservedProperties

## addNewObservedProperty

```csharp

Service service = new Service ("http://example.org/OGCSensorThings/v1.0");
string response = service.addNewObservedProperty ("noise level of the office", "Noise level", "http://www.qudt.org/qudt/owl/1.0.0/quantity/Instances.html#Noise");

Console.Out.WriteLine(response);

```

><button id="btn" onclick="show('#opExample1')">Show Response</button><div id="opExample1" class="exampleStyle" style="display: none;">
{<span class="textIndent"><br>
	"@iot.selfLink":"http://example.org/OGCSensorThings/v1.0/ObservedProperties(97241)",<br>
	"Datastreams@iot.navigationLink":"../ObservedProperties(97241)/Datastreams",<br>
	"@iot.id":97241,<br>
	"name":"Noise level",<br>
	"description":"noise level of the office",<br>
	"definition":"http://www.qudt.org/qudt/owl/1.0.0/quantity/Instances.html#Noise"</span><br>
}</div>

Create new ObservedProperty entity in OGC SensorThings database.

**Parameters**

*description:* A description of the ObservedProperty.

*name:* The name of the ObservedProperty entity.

*definition:* The definition of the ObservedProperty entity.

**Returns**

JSON string of the new ObservedProperty entity or error message if new record is not added.


Parameters | Type | Required
-------------- | -------------- | --------------
description | string | mandatory
name | string | optional
definition | long | optional


## addNewObservedPropertyByJSON

```csharp

Service service = new Service ("http://example.org/OGCSensorThings/v1.0");
string jsonString="{
		\"description\": \"Noise level of the building\", 
		\"name\": \"Noise level\", 
		\"definition\": \"http://www.qudt.org/qudt/owl/1.0.0/quantity/Instances.html#Noise\"
	}";

string response = service.addNewObservedPropertyByJSON (jsonString);

Console.Out.WriteLine(response);

```

><button id="btn" onclick="show('#opExample2')">Show Response</button><div id="opExample2" class="exampleStyle" style="display: none;">
{<span class="textIndent"><br>
	"@iot.selfLink":"http://example.org/OGCSensorThings/v1.0/ObservedProperties(97278)",<br>
	"Datastreams@iot.navigationLink":"../ObservedProperties(97278)/Datastreams",<br>
	"@iot.id":97278,<br>
	"name":"Noise level",<br>
	"description":"Noise level of the building",<br>
	"definition":"http://www.qudt.org/qudt/owl/1.0.0/quantity/Instances.html#Noise"</span><br>
}</div>

Create new ObservedProperty entity in OGC SensorThings database.

**Parameters**

*jsonString:* A JSON string describing the new ObservedProperty entity to be created.

**Returns**

JSON string of the new ObservedProperty entity or Error message if new record is not added.


Parameters | Type | Required
-------------- | -------------- | --------------
jsonString | string | mandatory


## deleteObservedProperty

```csharp

Service service = new Service ("http://example.org/OGCSensorThings/v1.0");
string value = service.deleteObservedProperty (97278);

Console.Out.WriteLine(response);

```

><button id="btn" onclick="show('#opExample3')">Show Output</button><div id="opExample3" class="exampleStyle" style="display: none;">
Succeeded: Record is deleted</div>

Delete ObservedProperty entity from the OGC SensorThings database.

**Parameters**

*id:* The id of the ObservedProperty entity to be deleted.

**Returns**

String showing the status of the delete operation.

Parameters | Type | Required
-------------- | -------------- | --------------
id | long | mandatory




## getObservedProperties

```csharp

Service service = new Service("http://example.org/OGCSensorThings/v1.0");
ArrayList array = service.getObservedProperties(0, 3)		//return the first three elements

foreach(ObservedProperty item in array){
	//print the properties
	Console.out.WriteLine("ID: "+item.id);
	Console.out.WriteLine("name: "+item.name);
	Console.out.WriteLine("description: "+item.description);
	Console.out.WriteLine("definition: "+item.definition);
}

```

><button id="btn" onclick="show('#opExample4')">Show Output</button><div id="opExample4" class="exampleStyle" style="display: none;">
ID: 66310<br>
name: Luminous Flux<br>
description: Luminous Flux or Luminous Power is the measure of the perceived power of light.<br>
definition: http://www.qudt.org/qudt/owl/1.0.0/quantity/Instances.html#LuminousFlux<br><br>
ID: 62868<br>
name: Noise levels<br>
description: Amount of ambient noise of the surroundings.<br>
definition: http://www.qudt.org/qudt/owl/1.0.0/quantity/Instances.html#Noise<br><br>
ID: 62839<br>
name: Humidity<br>
description: 123<br>
definition: https://www.auto.tuwien.ac.at/downloads/thinkhome/ontology/WeatherOntology.owl#hasHumidity</div>

Returns an ArrayList of ObservedProperty objects according to the specified skip and top values.

**Parameters**

*skip:* Indicate the number of records to be skiped from the begining of the returned list from the server.

*top:* Indicate the maximum number of records to be returned.

**Returns**

An ArrayList of ObservedProperty objects

Parameters | Type | Required
-------------- | -------------- | --------------
skip | int | mandatory
top | int | mandatory


## getObservedPropertiesJSON

```csharp

Service service = new Service("http://example.org/OGCSensorThings/v1.0");
string json = service.getObservedPropertiesJSON(3, 10,"id","","","id",false);		//skip the first three elements and return 10 elements only displaying id, order by id, and don't return the count. 

//print the json string to console
Console.out.WriteLine(json);

```

><button id="btn" onclick="show('#opExample5')">Show Response</button><div id="opExample5" class="exampleStyle" style="display: none;">
{<br><span class="textIndent">
"@iot.nextLink":"http://example.org/OGCSensorThings/v1.0/ObservedProperties?$skip=13&$top=10&$expand=id&$filter=&$orderby=id&$count=False",<br>
"value":[{<span class="textIndent"><br>
"@iot.selfLink":"http://example.org/OGCSensorThings/v1.0/ObservedProperties(32)",<br>
"Datastreams@iot.navigationLink":"../ObservedProperties(32)/Datastreams",<br>
"@iot.id":32,<br>
"name":"Luminous Flux",<br>
"description":"Luminous Flux or Luminous Power is the measure of the perceived power of light.",<br>
"definition":"http://www.qudt.org/qudt/owl/1.0.0/quantity/Instances.html#LuminousFlux"</span>
},<br>
{<br><span class="textIndent">
"@iot.selfLink":"http://example.org/OGCSensorThings/v1.0/ObservedProperties(42)",<br>
"Datastreams@iot.navigationLink":"../ObservedProperties(42)/Datastreams",<br>
"@iot.id":42,<br>
"name":"Office Temperature",<br>
"description":"Temperature of the surrounding sensor.",<br>
"definition":"http://www.qudt.org/qudt/owl/1.0.0/quantity/Instances.html#Temperature"</span>
},<br>......<br>]</span></span><br>
}</div>

Returns a JSON string of ObservedProperty records according to the specified skip, top, expand, select, filter, orderby, and count values.

**Parameters**

*skip:* Indicate the number of records to be skiped from the begining of the returned list from the server.

*top:* Indicate the maximum number of records to be returned.

*expand:* Indicates the related entities to be represented inline. Its value is a comma seperated list of navigation property names (e.g. "parameter1, parameter2").

*select:* Indicates which propeties to be returned explicitly. Its value is a comma seperated list of navigation property names (e.g. "parameter1, parameter2")

*filter:* Allows clients to filter a collection of entities that are addressed by a request URL.

*orderby:* Specifies the order in which items are returned from the service. Its value is a comma seperated list of navigation property names (e.g. "parameter1, parameter2")

*count:* A boolean value that specifies whether the total count of items be returned along with the result or not.

**Returns**

A JSON string of the requested ObservedProperty records.

Parameters | Type | Required
-------------- | -------------- | --------------
skip | int | mandatory
top | int | mandatory
expand | string | mandatory
filter | string | mandatory
orderby | string | mandatory
count | boolean | mandatory

## getObservedPropertyById

```csharp

Service service = new Service("http://example.org/OGCSensorThings/v1.0");
ObservedProperty op = service.getObservedPropertyById(66310); 

//print to console the properties of location
Console.out.WriteLine("ID: "+op.id);
Console.out.WriteLine("name: "+op.name);
Console.out.WriteLine("definition: "+op.definition);
Console.out.WriteLine("description: "+op.description);

```

><button id="btn" onclick="show('#opExample6')">Show Output</button><div id="opExample6" class="exampleStyle" style="display: none;">
ID: 66310<br>
name: Luminous Flux<br>
definition: http://www.qudt.org/qudt/owl/1.0.0/quantity/Instances.html#LuminousFlux<br>
description: Luminous Flux or Luminous Power is the measure of the perceived power of light.</div>

Returns a ObservedProperty object of the given id parameter.

**Parameters**

*id:* The id of the requested ObservedProperty entity.

**Returns**

A ObservedProperty object

Parameters | Type | Required
-------------- | -------------- | --------------
id | long | mandatory


## getObservedPropertyByIdJSON

```csharp

Service service = new Service("http://example.org/OGCSensorThings/v1.0");
string json = service.getObservedPropertyByIdJSON(66310); 

//print to JSON string to console
Console.out.WriteLine(json);

```

><button id="btn" onclick="show('#opExample7')">Show Output</button><div id="opExample7" class="exampleStyle" style="display: none;">
{<span class="textIndent"><br>
"@iot.selfLink":"http://example.org/OGCSensorThings/v1.0/ObservedProperties(66310)",<br>
"Datastreams@iot.navigationLink":"../ObservedProperties(66310)/Datastreams",<br>
"@iot.id":66310,<br>
"name":"Luminous Flux",<br>
"description":"Luminous Flux or Luminous Power is the measure of the perceived power of light.",<br>
"definition":"http://www.qudt.org/qudt/owl/1.0.0/quantity/Instances.html#LuminousFlux"</span><br>
}</div>

Returns a JSON string of the ObservedProperty record by the given id parameter.

**Parameters**

*id:* The id of the requested ObservedProperty entity.

**Returns**

A JSON string of the requested ObservedProperty entity

Parameters | Type | Required
-------------- | -------------- | --------------
id | long | mandatory
