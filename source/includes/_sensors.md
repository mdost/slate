<script type="text/javascript" src="../javascripts/sensorup.js"></script>
<link rel="stylesheet" type="text/css" href="../stylesheets/sensorup.css">

# Sensors

## addNewSensor

```csharp
Service service = new Service ("http://example.org/OGCSensorThings/v1.0");
string response = service.addNewSensor ("Acme Fluxomatic 1000","http://schema.org/description","Light flux sensor");
Console.Out.WriteLine(response);

```

><button id="btn" onclick="show('#sensorExample1')">Show Response</button><div id="sensorExample1" class="exampleStyle" style="display: none;">
{<span class="textIndent"><br>
  "metadata":"Light flux sensor",<br>
  "@iot.selfLink":"http://example.org/OGCSensorThings/v1.0/Sensors(114457)",<br>
  "Datastreams@iot.navigationLink":"../Sensors(114457)/Datastreams",<br>
  "@iot.id":114457,"encodingType":"http://schema.org/description",<br>
  "description":"Acme Fluxomatic 1000"</span><br>
}</div>

Create new Sensor entity in OGC SensorThings database.

**Parameters**

*description:* A description of the Sensor.

*encodingType:* The encodingType of the Sensor.

*metadata:* The metadata of the Sensor.

**Returns**

JSON string of the new Sensor entity or error message if new record is not added.


Parameters | Type | Required
-------------- | -------------- | --------------
description | string | mandatory
properties | string | optional
locationID | long | optional


## addNewSensorByJSON

```csharp
Service service = new Service ("http://example.org/OGCSensorThings/v1.0");
string jsonString ="{ 
      \"description\": \"Acme Fluxomatic 1000\", 
      \"encodingType\": \"http://schema.org/description\", 
      \"metadata\": \"Light flux sensor\"
    }";

string response = service.addNewSensorByJSON (jsonString);

Console.Out.WriteLine(response);

```
><button id="btn" onclick="show('#sensorExample2')">Show Response</button><div id="sensorExample2" class="exampleStyle" style="display: none;">
{<span class="textIndent"><br>
  "metadata":"Light flux sensor",<br>
  "@iot.selfLink":"http://example.org/OGCSensorThings/v1.0/Sensors(114482)",<br>
  "Datastreams@iot.navigationLink":"../Sensors(114457)/Datastreams",<br>
  "@iot.id":114457,"encodingType":"http://schema.org/description",<br>
  "description":"Acme Fluxomatic 1000"</span><br>
}</div>

Create new Sensor entity in OGC SensorThings database.

**Parameters**

*jsonString:* A JSON string describing the new Sensor entity to be created.

**Returns**

JSON string of the new Sensor entity or error message if new record is not added.


Parameters | Type | Required
-------------- | -------------- | --------------
jsonString | string | mandatory


## deleteSensor

```csharp
Service service = new Service ("http://example.org/OGCSensorThings/v1.0");
string response = service.deleteSensor (66309);
Console.Out.WriteLine(response);

```
><button id="btn" onclick="show('#sensorExample3')">Show Response</button><div id="sensorExample3" class="exampleStyle" style="display: none;">
Succeeded: Record is deleted</div>

Delete Sensor entity from the OGC SensorThings database.

**Parameters**

*id:* The id of the Sensor entity to be deleted.

**Returns**

String showing the status of the delete operation.

Parameters | Type | Required
-------------- | -------------- | --------------
id | long | mandatory


## setSensorDescription

```csharp
Service service = new Service ("http://example.org/OGCSensorThings/v1.0");
string response = service.setSensorDescription (62869,"Sensor of the office.");

Console.Out.WriteLine(response);

```
><button id="btn" onclick="show('#sensorExample4')">Show Response</button><div id="sensorExample4" class="exampleStyle" style="display: none;">
{<span class="textIndent"><br>
  "metadata":"http://cdn.sparkfun.com/datasheets/Sensors/Sound/CEM-C9745JAD462P2.54R.pdf",<br>
  "@iot.selfLink":"http://example.org/OGCSensorThings/v1.0/Sensors(62869)",<br>
  "Datastreams@iot.navigationLink":"../Sensors(62869)/Datastreams",<br>
  "@iot.id":62869,<br>
  "encodingType":"http://schema.org/description",<br>
  "description":"Sensor of the office."</span><br>
}</div>

Update the Description of a Sensor entity.

**Parameters**

*id:* The id of the Sensor entity to be updated.

*description:* A description of the Sensor.

**Returns**

String showing the updated status.

Parameters | Type | Required
-------------- | -------------- | --------------
id | long | mandatory
description | string | mandatory

## setSensorEncodingType

```csharp
Service service = new Service ("http://example.org/OGCSensorThings/v1.0");
string response = service.setSensorEncodingType (62869,"application/pdf");

Console.Out.WriteLine(response);

```
><button id="btn" onclick="show('#sensorExample5')">Show Response</button><div id="sensorExample5" class="exampleStyle" style="display: none;">
{<span class="textIndent"><br>
  "metadata":"http://cdn.sparkfun.com/datasheets/Sensors/Sound/CEM-C9745JAD462P2.54R.pdf",<br>
  "@iot.selfLink":"http://example.org/OGCSensorThings/v1.0/Sensors(62869)",<br>
  "Datastreams@iot.navigationLink":"../Sensors(62869)/Datastreams",<br>
  "@iot.id":62869,<br>
  "encodingType":"application/pdf",<br>
  "description":"Sensor of the office."</span><br>
}</div>

Update the encoding type of a Sensor entity.

**Parameters**

*id:* The id of the Sensor entity to be updated.

*encodingType:* The new encoding type of the Sensor.

**Returns**

String showing the updated status.

Parameters | Type | Required
-------------- | -------------- | --------------
id | long | mandatory
encodingType | string | mandatory

## setSensorMetadata

```csharp
Service service = new Service ("http://example.org/OGCSensorThings/v1.0");
string response = service.setSensorMetadata (62869,"Light flux sensor");

Console.Out.WriteLine(response);

```
><button id="btn" onclick="show('#sensorExample6')">Show Response</button><div id="sensorExample6" class="exampleStyle" style="display: none;">
{<span class="textIndent"><br>
  "metadata":"Light flux sensor",<br>
  "@iot.selfLink":"http://example.org/OGCSensorThings/v1.0/Sensors(62869)",<br>
  "Datastreams@iot.navigationLink":"../Sensors(62869)/Datastreams",<br>
  "@iot.id":62869,<br>
  "encodingType":"application/pdf",<br>
  "description":"Sensor of the office."</span><br>
}</div>

Update the metadata of a Sensor entity.

**Parameters**

*id:* The id of the Sensor entity to be updated.

*metadata:* The new encoding type of the Sensor.

**Returns**

String showing the updated status.

Parameters | Type | Required
-------------- | -------------- | --------------
id | long | mandatory
metadata | string | mandatory




## getSensors

```csharp

Service service = new Service("http://example.org/OGCSensorThings/v1.0");
ArrayList array = service.getSensors(30, 2)		//skip the first 30 elements and return the next 10 elements

foreach(Sensor item in array){
	//print the properties
	Console.out.WriteLine("ID: "+item.id);
	Console.out.WriteLine("Metadata: "+item.metadata);
	Console.out.WriteLine("Description: "+item.description);
}

```
><button id="btn" onclick="show('#sensorExample7')">Show Response</button><div id="sensorExample7" class="exampleStyle" style="display: none;">
ID: 114482<br>
Metadata: Light flux sensor<br>
Description: Acme Fluxomatic 1000<br>
ID: 62869<br>
Metadata: http://cdn.sparkfun.com/datasheets/Sensors/Sound/CEM-C9745JAD462P2.54R.pdf<br>
Description: Sensor of the office.<br>
</div>

Returns an ArrayList of Sensor objects according to the specified skip and top values.

**Parameters**

*skip:* Indicate the number of records to be skiped from the begining of the returned list from the server.

*top:* Indicate the maximum number of records to be returned.

**Returns**

An ArrayList of Sensor objects

Parameters | Type | Required
-------------- | -------------- | --------------
skip | int | mandatory
top | int | mandatory


## getSensorsJSON

```csharp

Service service = new Service("http://example.org/OGCSensorThings/v1.0");
string json = service.getSensorsJSON(3, 1, "","id","id gt 10000","id",false);		//skip the first three elements and return one element only displaying id, filter id's that are greater than 10000, order by id, and don't return the count. 

//print the json string to console
Console.out.WriteLine(json);

```
><button id="btn" onclick="show('#sensorExample8')">Show Response</button><div id="sensorExample8" class="exampleStyle" style="display: none;">
{<span class="textIndent"><br>
  "@iot.nextLink":"http://example.org/OGCSensorThings/v1.0/Sensors?$skip=3&$top=1&$expand=&$filter=id gt 1000&$orderby=id&$count=False&$select=id",<br>
  "value":[<span class="textIndent">
    {"id":62869},</span><br>
  ]</span><br>
}</div>

Returns a JSON string of Sensor records according to the specified skip, top, expand, select, filter, orderby, and count values.

**Parameters**

*skip:* Indicate the number of records to be skiped from the begining of the returned list from the server.

*top:* Indicate the maximum number of records to be returned.

*expand:* Indicates the related entities to be represented inline. Its value is a comma seperated list of navigation property names (e.g. "parameter1, parameter2").

*select:* Indicates which propeties to be returned explicitly. Its value is a comma seperated list of navigation property names (e.g. "parameter1, parameter2")

*filter:* Allows clients to filter a collection of entities that are addressed by a request URL.

*orderby:* Specifies the order in which items are returned from the service. Its value is a comma seperated list of navigation property names (e.g. "parameter1, parameter2")

*count:* A boolean value that specifies whether the total count of items be returned along with the result or not.

**Returns**

A JSON string of the requested Sensor records.

Parameters | Type | Required
-------------- | -------------- | --------------
skip | int | mandatory
top | int | mandatory
expand | string | mandatory
filter | string | mandatory
orderby | string | mandatory
count | boolean | mandatory

## getSensorById

```csharp

Service service = new Service("http://example.org/OGCSensorThings/v1.0");
Sensor sensor = service.getSensorById(62869); 

//print to console the properties of location
Console.out.WriteLine("ID: "+sensor.id);
Console.out.WriteLine("description: "+sensor.description);
Console.out.WriteLine("metadata: "+sensor.metadata);

```
><button id="btn" onclick="show('#sensorExample9')">Show Response</button><div id="sensorExample9" class="exampleStyle" style="display: none;">
ID: 62869<br>
description: Sensor of the office.<br>
encodingType: application/pdf<br>
metadata: http://cdn.sparkfun.com/datasheets/Sensors/Sound/CEM-C9745JAD462P2.54R.pdf<br>
</div>

Returns a Sensor object of the given id parameter.

**Parameters**

*id:* The id of the requested Sensor entity.

**Returns**

A Sensor object

Parameters | Type | Required
-------------- | -------------- | --------------
id | long | mandatory


## getSensorByIdJSON

```csharp

Service service = new Service("http://example.org/OGCSensorThings/v1.0");
string json = service.getSensorByIdJSON(62848); 

//print to JSON string to console
Console.out.WriteLine(json);

```
><button id="btn" onclick="show('#sensorExample10')">Show Response</button><div id="sensorExample10" class="exampleStyle" style="display: none;">
{<span class="textIndent"><br>
  "metadata": "http://cdn.sparkfun.com/datasheets/Sensors/Sound/CEM-C9745JAD462P2.54R.pdf",<br>
  "@iot.selfLink": "http://example.org/OGCSensorThings/v1.0/Sensors(62848)",<br>
  "Datastreams@iot.navigationLink": "../Sensors(62848)/Datastreams",<br>
  "@iot.id": 62848,<br>
  "encodingType": "application/pdf",<br>
  "description": "This is a Sound Level Sensor"</span><br>
}</div>

Returns a JSON string of the Sensor record by the given id parameter.

**Parameters**

*id:* The id of the requested Sensor entity.

**Returns**

A JSON string of the requested Sensor entity

Parameters | Type | Required
-------------- | -------------- | --------------
id | long | mandatory
