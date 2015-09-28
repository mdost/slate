<script type="text/javascript" src="../javascripts/sensorup.js"></script>
<link rel="stylesheet" type="text/css" href="../stylesheets/sensorup.css">

# Datastreams

## addNewDatastream

```csharp
Service service = new Service ("http://example.org/OGCSensorThings/v1.0");

string response = service.addNewDatastream ("Light exposure.", "{\"symbol\": \"lm3\",\"name\": \"Lume3n\",\"definition\": \"http://w3ww.qudt.org/qudt/owl/1.0.0/unit/Instances.html#Lumen\"}", "http://www.opengis.net/def/observationType/OGC-OM/2.0/OM_Measurement", 114482, 97494, 97241);

Console.Out.WriteLine(response);

```

><button id="btn" onclick="show('#dtExample1')">Show Response</button><div id="dtExample1" class="exampleStyle" style="display: none;">
{<span class="textIndent"><br>
  "unitOfMeasurement":{<span class="textIndent">
      "symbol":"lm3",<br>
      "name":"Lume3n",<br>
      "definition":"http://w3ww.qudt.org/qudt/owl/1.0.0/unit/Instances.html#Lumen"</span><br>
    },<br>
    "@iot.selfLink":"http://example.org/OGCSensorThings/v1.0/Datastreams(115529)",<br>
    "Thing@iot.navigationLink":"../Datastreams(115529)/Thing",<br>
    "Sensor@iot.navigationLink":"../Datastreams(115529)/Sensor",<br>
    "observationType":"http://www.opengis.net/def/observationType/OGC-OM/2.0/OM_Measurement",<br>
    "@iot.id":115529,<br>
    "description":"Light exposure.",<br>
    "Observations@iot.navigationLink":"../Datastreams(115529)/Observations",<br>
    "ObservedProperty@iot.navigationLink":"../Datastreams(115529)/ObservedProperty"</span><br>
}</div>

Create new Datastream entity in OGC SensorThings database.

**Parameters**

*description:* A description of the Datastream.

*unitOfMeasurement:* The unitOfMeasurement of the Datastream entity.

*observationType:* The observationType of the Datastream entity.

*sensorId:* The id of the Sensor to be associated with the new Datastream entity.

*thingId:* The id of the Thing to be associated with the new Datastream entity.

*observedPropertyId:* The id of the ObservedProperty to be associated with the new Datastream entity.


**Returns**

JSON string of the new Datastream entity or error message if new record is not added.


Parameters | Type | Required
-------------- | -------------- | --------------
description | string | mandatory
unitOfMeasurement | string | mandatory
observationType | long | mandatory
sensorId | long | optional
thingId | long | optional
observedPropertyId | long | optional


## addNewDatastreamByJSON

```csharp
Service service = new Service ("http://example.org/OGCSensorThings/v1.0");

string jsonString="{
    \"unitOfMeasurement\": {
        \"symbol\": \"lm3\",
        \"name\": \"Lume3n\",
        \"definition\": \"http://w3ww.qudt.org/qudt/owl/1.0.0/unit/Instances.html#Lumen\"
      },
      \"description\": \"Light exposure.\",
      \"observationType\": \"http://www.opengis.net/def/observationType/OGC-OM/2.0/OM_Measurement\",
      \"Sensor\":{\"@iot.id\": 114482}, 
      \"Thing\":{\"@iot.id\": 97494},
      \"ObservedProperty\":{\"@iot.id\": 97241}
  }";

string response = service.addNewDatastreamByJSON (jsonString);

Console.Out.WriteLine(response);

```

><button id="btn" onclick="show('#dtExample2')">Show Response</button><div id="dtExample2" class="exampleStyle" style="display: none;">
{<span class="textIndent"><br>
  "unitOfMeasurement":{<span class="textIndent">
      "symbol":"lm3",<br>
      "name":"Lume3n",<br>
      "definition":"http://w3ww.qudt.org/qudt/owl/1.0.0/unit/Instances.html#Lumen"</span><br>
    },<br>
    "@iot.selfLink":"http://example.org/OGCSensorThings/v1.0/Datastreams(115529)",<br>
    "Thing@iot.navigationLink":"../Datastreams(115529)/Thing",<br>
    "Sensor@iot.navigationLink":"../Datastreams(115529)/Sensor",<br>
    "observationType":"http://www.opengis.net/def/observationType/OGC-OM/2.0/OM_Measurement",<br>
    "@iot.id":115584,<br>
    "description":"Light exposure.",<br>
    "Observations@iot.navigationLink":"../Datastreams(115529)/Observations",<br>
    "ObservedProperty@iot.navigationLink":"../Datastreams(115529)/ObservedProperty"</span><br>
}</div>

Create new Datastream entity in OGC SensorThings database.

**Parameters**

*jsonString:* A JSON string describing the new Datastream entity to be created.


**Returns**

JSON string of the new Datastream entity or error message if new record is not added.


Parameters | Type | Required
-------------- | -------------- | --------------
jsonString | string | mandatory


## deleteDatastream

```csharp
Service service = new Service ("http://example.org/OGCSensorThings/v1.0");
string response = service.deleteDatastream (115584);
Console.Out.WriteLine(response);

```
><button id="btn" onclick="show('#dtExample3')">Show Response</button><div id="dtExample3" class="exampleStyle" style="display: none;">
Succeeded: Record is deleted</div>

Delete Datastream entity from the OGC SensorThings database.

**Parameters**

*id:* The id of the Datastream entity to be deleted.

**Returns**

String showing the status of the delete operation.

Parameters | Type | Required
-------------- | -------------- | --------------
id | long | mandatory


## setDatastreamDescription

```csharp
Service service = new Service ("http://example.org/OGCSensorThings/v1.0");
string response = service.setDatastreamDescription (115528, "Sound");
Console.Out.WriteLine(response);

```
><button id="btn" onclick="show('#dtExample4')">Show Response</button><div id="dtExample4" class="exampleStyle" style="display: none;">
{<span class="textIndent"><br>
  "unitOfMeasurement":{<span class="textIndent">
      "symbol":"lm3",<br>
      "name":"Lume3n",<br>
      "definition":"http://w3ww.qudt.org/qudt/owl/1.0.0/unit/Instances.html#Lumen"<br></span>
    },<br>
    "@iot.selfLink":"http://example.org/OGCSensorThings/v1.0/Datastreams(115528)",<br>
    "Thing@iot.navigationLink":"../Datastreams(115528)/Thing",<br>
    "Sensor@iot.navigationLink":"../Datastreams(115528)/Sensor",<br>
    "observationType":"http://www.opengis.net/def/observationType/OGC-OM/2.0/OM_Measurement",<br>
    "@iot.id":115528,<br>
    "description":"Sound",<br>
    "Observations@iot.navigationLink":"../Datastreams(115528)/Observations",<br>
    "ObservedProperty@iot.navigationLink":"../Datastreams(115528)/ObservedProperty"<br></span>
}</div>

Update the description of a Datastream entity.

**Parameters**

*id:* The id of the Datastream entity to be updated.

*description:* A description of the Datastream.

**Returns**

String showing the updated status.

Parameters | Type | Required
-------------- | -------------- | --------------
id | long | mandatory
description | string | mandatory

## setDatastreamUnitOfMeasurement

```csharp
Service service = new Service ("http://example.org/OGCSensorThings/v1.0");

string response = service.setDatastreamUnitOfMeasurement (115528, "\"symbol\": \"db\",\"name\": \"decibles\",\"definition\": \"http://www.qudt.org/qudt/owl/1.0.0/unit/Instances.html#altitude\"");

Console.Out.WriteLine(response);

```
><button id="btn" onclick="show('#dtExample5')">Show Response</button><div id="dtExample5" class="exampleStyle" style="display: none;">
{<span class="textIndent"><br>
  "unitOfMeasurement":{<span class="textIndent">
      "symbol": "db",<br>
      "name": "decibles",<br>
      "definition": "http://www.qudt.org/qudt/owl/1.0.0/unit/Instances.html#altitude"<br></span>
    },<br>
    "@iot.selfLink":"http://example.org/OGCSensorThings/v1.0/Datastreams(115528)",<br>
    "Thing@iot.navigationLink":"../Datastreams(115528)/Thing",<br>
    "Sensor@iot.navigationLink":"../Datastreams(115528)/Sensor",<br>
    "observationType":"http://www.opengis.net/def/observationType/OGC-OM/2.0/OM_Measurement",<br>
    "@iot.id":115528,<br>
    "description":"Sound",<br>
    "Observations@iot.navigationLink":"../Datastreams(115528)/Observations",<br>
    "ObservedProperty@iot.navigationLink":"../Datastreams(115528)/ObservedProperty"<br></span>
}</div>

Update the unit of measurement of a Datastream entity.

**Parameters**

*id:* The id of the Datastream entity to be updated.

*unitOfMeasurement:* The new unit of measurement of the Datastream entity.

**Returns**

String showing the updated status.

Parameters | Type | Required
-------------- | -------------- | --------------
id | long | mandatory
unitOfMeasurement | string | mandatory

## setDatastreamObservationType

```csharp
Service service = new Service ("http://example.org/OGCSensorThings/v1.0");
string response = service.setDatastreamObservationType (115528, "http://www.opengis.net/def/observationType/OGC-OM/2.0/OM_Measurement");

Console.Out.WriteLine(response);

```
><button id="btn" onclick="show('#dtExample6')">Show Response</button><div id="dtExample6" class="exampleStyle" style="display: none;">
{<span class="textIndent"><br>
  "unitOfMeasurement":{<span class="textIndent">
      "symbol": "db",<br>
      "name": "decibles",<br>
      "definition": "http://www.qudt.org/qudt/owl/1.0.0/unit/Instances.html#altitude"<br></span>
    },<br>
    "@iot.selfLink":"http://example.org/OGCSensorThings/v1.0/Datastreams(115528)",<br>
    "Thing@iot.navigationLink":"../Datastreams(115528)/Thing",<br>
    "Sensor@iot.navigationLink":"../Datastreams(115528)/Sensor",<br>
    "observationType":"http://www.opengis.net/def/observationType/OGC-OM/2.0/OM_Measurement",<br>
    "@iot.id":115528,<br>
    "description":"Sound",<br>
    "Observations@iot.navigationLink":"../Datastreams(115528)/Observations",<br>
    "ObservedProperty@iot.navigationLink":"../Datastreams(115528)/ObservedProperty"<br></span>
}</div>

Update the observation type of a Datastream entity.

**Parameters**

*id:* The id of the Datastream entity to be updated.

*observationType:* The new observation type of the Datastream entity.

**Returns**

String showing the updated status.

Parameters | Type | Required
-------------- | -------------- | --------------
id | long | mandatory
observationType | string | mandatory



## getDatastreams

```csharp

Service service = new Service("http://example.org/OGCSensorThings/v1.0");
ArrayList array = service.getDatastreams(0, 3)		//return the first 10 elements

foreach(Datastream item in array){
	//print the properties
	Console.out.WriteLine("ID: "+item.id);
	Console.out.WriteLine("observationType: "+item.observationType);
}

```
><button id="btn" onclick="show('#dtExample7')">Show Response</button><div id="dtExample7" class="exampleStyle" style="display: none;">
ID: 115584<br>
observationType: http://www.opengis.net/def/observationType/OGC-OM/2.0/OM_Measurement<br>
ID: 115529<br>
observationType: http://www.opengis.net/def/observationType/OGC-OM/2.0/OM_Measurement<br>
ID: 115528<br>
observationType: http://www.opengis.net/def/observationType/OGC-OM/2.0/OM_Measurement<br>
</div>

Returns an ArrayList of Datastream objects according to the specified skip and top values.

**Parameters**

*skip:* Indicate the number of records to be skiped from the begining of the returned list from the server.

*top:* Indicate the maximum number of records to be returned.

**Returns**

An ArrayList of Datastream objects

Parameters | Type | Required
-------------- | -------------- | --------------
skip | int | mandatory
top | int | mandatory


## getDatastreamsJSON

```csharp

Service service = new Service("http://example.org/OGCSensorThings/v1.0");
string json = service.getDatastreamsJSON(4, 1, "Thing","","id gt 10000","id",true);

//print the json string to console
Console.out.WriteLine(json);

```
><button id="btn" onclick="show('#dtExample8')">Show Response</button><div id="dtExample8" class="exampleStyle" style="display: none;">
{<span class="textIndent"><br>
  "@iot.nextLink": "http://example.org/OGCSensorThings/v1.0/Datastreams?$skip=6&$top=1&$expand=Thing&$filter=id gt 10000&$orderby=id&$count=True",<br>
  "count": 77,<br>
  "value": [<br>
    {<span class="textIndent"><br>
      "unitOfMeasurement": {<span class="textIndent">
        "symbol": "",<br>
        "name": "Ralated Atmosphere",<br>
        "definition": "http://www.qudt.org/qudt/owl/1.0.0/unit/Instances.html#Lumen"</span><br>
      },<br>
      "@iot.selfLink": "http://example.org/OGCSensorThings/v1.0/Datastreams(14054)",<br>
      "Sensor@iot.navigationLink": "../Datastreams(14054)/Sensor",<br>
      "observationType": "http://www.opengis.net/def/observationType/OGC-OM/2.0/OM_Measurement",<br>
      "@iot.id": 14054,<br>
      "description": "Ralated Atmosphere",<br>
      "Observations@iot.navigationLink": "../Datastreams(14054)/Observations",<br>
      "ObservedProperty@iot.navigationLink": "../Datastreams(14054)/ObservedProperty",<br>
      "Thing": {<span class="textIndent"><br>
        "@iot.selfLink": "http://example.org/OGCSensorThings/v1.0/Things(14050)",<br>
        "@iot.id": 14050,<br>
        "description": "Office Building",<br>
        "properties": {<span class="textIndent">
          "reference": "Third Floor"</span><br>
        }</span><br>
      }<br>
    ]</span><br>
}</div>

Returns a JSON string of Datastream records according to the specified skip, top, expand, select, filter, orderby, and count values.

**Parameters**

*skip:* Indicate the number of records to be skiped from the begining of the returned list from the server.

*top:* Indicate the maximum number of records to be returned.

*expand:* Indicates the related entities to be represented inline. Its value is a comma seperated list of navigation property names (e.g. "parameter1, parameter2").

*select:* Indicates which propeties to be returned explicitly. Its value is a comma seperated list of navigation property names (e.g. "parameter1, parameter2")

*filter:* Allows clients to filter a collection of entities that are addressed by a request URL.

*orderby:* Specifies the order in which items are returned from the service. Its value is a comma seperated list of navigation property names (e.g. "parameter1, parameter2")

*count:* A boolean value that specifies whether the total count of items be returned along with the result or not.

**Returns**

A JSON string of the requested Datastream records.

Parameters | Type | Required
-------------- | -------------- | --------------
skip | int | mandatory
top | int | mandatory
expand | string | mandatory
filter | string | mandatory
orderby | string | mandatory
count | boolean | mandatory

## getDatastreamById

```csharp

Service service = new Service("http://example.org/OGCSensorThings/v1.0");
Datastream dt = service.getDatastreamById(62888); 

//print to console the properties of location
Console.out.WriteLine("ID: "+dt.id);
Console.out.WriteLine("description: "+dt.description);
Console.out.WriteLine("observationType: "+dt.observationType);
Console.out.WriteLine("Result Time: "+dt.resultTime);
Console.out.WriteLine("Phenonmenon Time: "+dt.phenomenonTime);


```
><button id="btn" onclick="show('#dtExample9')">Show Response</button><div id="dtExample9" class="exampleStyle" style="display: none;">
ID: 62888<br>
description: Sound.<br>
Observation Type: http://www.opengis.net/def/observationType/OGC-OM/2.0/OM_Measurement<br>
Result Time: 0001-01-01 12:00:00 AM<br>
Phenonmenon Time: 0001-01-01 12:00:00 AM<br>
</div>

Returns a Datastream object of the given id parameter.

**Parameters**

*id:* The id of the requested Datastream entity.

**Returns**

A Datastream object

Parameters | Type | Required
-------------- | -------------- | --------------
id | long | mandatory


## getDatastreamByIdJSON

```csharp

Service service = new Service("http://example.org/OGCSensorThings/v1.0");
string json = service.getDatastreamByIdJSON(62888); 

//print to JSON string to console
Console.out.WriteLine(json);

```
><button id="btn" onclick="show('#dtExample10')">Show Response</button><div id="dtExample10" class="exampleStyle" style="display: none;">
{<span class="textIndent"><br>
  "unitOfMeasurement": {<span class="textIndent">
    "symbol": "db",<br>
    "name": "decibles",<br>
    "definition": "http://www.qudt.org/qudt/owl/1.0.0/unit/Instances.html#altitude"</span><br>
  },<br>
  "@iot.selfLink": "http://example.org/OGCSensorThings/v1.0/Datastreams(62888)",<br>
  "Thing@iot.navigationLink": "../Datastreams(62888)/Thing",<br>
  "Sensor@iot.navigationLink": "../Datastreams(62888)/Sensor",<br>
  "observationType": "http://www.opengis.net/def/observationType/OGC-OM/2.0/OM_Measurement",<br>
  "@iot.id": 62888,<br>
  "description": "Sound.",<br>
  "Observations@iot.navigationLink": "../Datastreams(62888)/Observations",<br>
  "ObservedProperty@iot.navigationLink": "../Datastreams(62888)/ObservedProperty"</span>
}</div>

Returns a JSON string of the Datastream record by the given id parameter.

**Parameters**

*id:* The id of the requested Datastream entity.

**Returns**

A JSON string of the requested Datastream entity

Parameters | Type | Required
-------------- | -------------- | --------------
id | long | mandatory


## getDatastreamsOfThing

```csharp

Service service = new Service("http://example.org/OGCSensorThings/v1.0");
ArrayList array = service.getDatastreamsOfThing(62887, 0, 1); 

//print to JSON string to console
foreach(Datastream item in array){
	//print the properties
	Console.out.WriteLine("ID: "+dt.id);
  Console.out.WriteLine("description: "+dt.description);
  Console.out.WriteLine("observationType: "+dt.observationType);
  Console.out.WriteLine("Result Time: "+dt.resultTime);
  Console.out.WriteLine("Phenonmenon Time: "+dt.phenomenonTime);
}

```
><button id="btn" onclick="show('#dtExample11')">Show Response</button><div id="dtExample11" class="exampleStyle" style="display: none;">
ID: 62888<br>
description: Sound.<br>
Observation Type: http://www.opengis.net/def/observationType/OGC-OM/2.0/OM_Measurement<br>
Result Time: 0001-01-01 12:00:00 AM<br>
Phenonmenon Time: 0001-01-01 12:00:00 AM<br>
</div>

Returns Datastream entities associated with the given Thing entity.

**Parameters**

*thingId:* The id of the Thing entity.

*skip:* Indicate the number of records to be skiped from the begining of the returned list from the server.

*top:* Indicate the maximum number of records to be returned.

**Returns**

An ArrayList of the requested Datastream objects.

Parameters | Type | Required
-------------- | -------------- | --------------
id | long | mandatory
skip | int | mandatory
top | int | mandatory

## getDatastreamsOfThingJSON

```csharp

Service service = new Service("http://example.org/OGCSensorThings/v1.0");
string json = service.getDatastreamsOfThingJSON(62887,5, 1,"","","","id",true); 

Console.out.WriteLine(json);

```
><button id="btn" onclick="show('#dtExample12')">Show Response</button><div id="dtExample12" class="exampleStyle" style="display: none;">
{<span class="textIndent"><br>
  "count": 1,<br>
  "value": [<br>
    {<span class="textIndent"><br>
      "unitOfMeasurement": {<span class="textIndent"><br>
        "symbol": "db",<br>
        "name": "decibles",<br>
        "definition": "http://www.qudt.org/qudt/owl/1.0.0/unit/Instances.html#altitude"<br></span>
      },</span>
      "@iot.selfLink": "http://example.org/OGCSensorThings/v1.0/Datastreams(62888)",<br>
      "Thing@iot.navigationLink": "../Datastreams(62888)/Thing",<br>
      "Sensor@iot.navigationLink": "../Datastreams(62888)/Sensor",<br>
      "observationType": "http://www.opengis.net/def/observationType/OGC-OM/2.0/OM_Measurement",<br>
      "@iot.id": 62888,<br>
      "description": "Sound.",<br>
      "Observations@iot.navigationLink": "../Datastreams(62888)/Observations",<br>
      "ObservedProperty@iot.navigationLink": "../Datastreams(62888)/ObservedProperty"<br>
    }<br>
  ]<br></span>
}</div>

Returns Datastream entities associated with the given Thing entity.

**Parameters**

*thingId:* The id of the Thing entity.

*skip:* Indicate the number of records to be skiped from the begining of the returned list from the server.

*top:* Indicate the maximum number of records to be returned.

*expand:* Indicates the related entities to be represented inline. Its value is a comma seperated list of navigation property names (e.g. "parameter1, parameter2").

*select:* Indicates which propeties to be returned explicitly. Its value is a comma seperated list of navigation property names (e.g. "parameter1, parameter2")

*filter:* Allows clients to filter a collection of entities that are addressed by a request URL.

*orderby:* Specifies the order in which items are returned from the service. Its value is a comma seperated list of navigation property names (e.g. "parameter1, parameter2")

*count:* A boolean value that specifies whether the total count of items be returned along with the result or not.

**Returns**

An ArrayList of the requested Datastream objects.

Parameters | Type | Required
-------------- | -------------- | --------------
id | long | mandatory
skip | int | mandatory
top | int | mandatory
expand | string | mandatory
filter | string | mandatory
orderby | string | mandatory
count | boolean | mandatory


## getDatastreamsOfSensor

```csharp

Service service = new Service("http://example.org/OGCSensorThings/v1.0");
ArrayList array = service.getDatastreamsOfSensor(62848, 0, 6); 

//print to JSON string to console
foreach(Datastream item in array){
	//print the properties
	Console.out.WriteLine("ID: "+dt.id);
  Console.out.WriteLine("description: "+dt.description);
  Console.out.WriteLine("observationType: "+dt.observationType);
  Console.out.WriteLine("Result Time: "+dt.resultTime);
  Console.out.WriteLine("Phenonmenon Time: "+dt.phenomenonTime);
}

```
><button id="btn" onclick="show('#dtExample13')">Show Response</button><div id="dtExample13" class="exampleStyle" style="display: none;">
ID: 62892<br>
description: Sound.<br>
Observation Type: http://www.opengis.net/def/observationType/OGC-OM/2.0/OM_Measurement<br>
result time: 0001-01-01 12:00:00 AM<br>
Phenonmenon Time: 0001-01-01 12:00:00 AM<br>
ID: 62888<br>
description: Sound.<br>
Observation Type: http://www.opengis.net/def/observationType/OGC-OM/2.0/OM_Measurement<br>
result time: 0001-01-01 12:00:00 AM<br>
Phenonmenon Time: 0001-01-01 12:00:00 AM<br>
ID: 62871<br>
description: Sound.<br>
Observation Type: http://www.opengis.net/def/observationType/OGC-OM/2.0/OM_Measurement<br>
result time: 0001-01-01 12:00:00 AM<br>
Phenonmenon Time: 0001-01-01 12:00:00 AM<br>..........</div>

Returns Datastream entities associated with the given Sensor entity.

**Parameters**

*sensorId:* The id of the Sensor entity.

*skip:* Indicate the number of records to be skiped from the begining of the returned list from the server.

*top:* Indicate the maximum number of records to be returned.

**Returns**

An ArrayList of the requested Datastream objects.

Parameters | Type | Required
-------------- | -------------- | --------------
id | long | mandatory
skip | int | mandatory
top | int | mandatory


## getDatastreamsOfSensorJSON

```csharp

Service service = new Service("http://example.org/OGCSensorThings/v1.0");
string json = service.getDatastreamsOfSensorJSON(62848, 4, 1,"","","","id",true); 

Console.out.WriteLine(json);

```
><button id="btn" onclick="show('#dtExample14')">Show Response</button><div id="dtExample14" class="exampleStyle" style="display: none;">
{<span class="textIndent"><br>
  "count": 1,<br>
  "value": [<br>
    {<span class="textIndent"><br>
      "unitOfMeasurement": {<span class="textIndent">
        "symbol": "db",<br>
        "name": "decibles",<br>
        "definition": "http://www.qudt.org/qudt/owl/1.0.0/unit/Instances.html#altitude"</span><br>
      },<br>
      "@iot.selfLink": "http://example.org/OGCSensorThings/v1.0/Datastreams(62892)",<br>
      "Thing@iot.navigationLink": "../Datastreams(62892)/Thing",<br>
      "Sensor@iot.navigationLink": "../Datastreams(62892)/Sensor",<br>
      "observationType": "http://www.opengis.net/def/observationType/OGC-OM/2.0/OM_Measurement",<br>
      "@iot.id": 62892,<br>
      "description": "Sound.",<br>
      "Observations@iot.navigationLink": "../Datastreams(62892)/Observations",<br>
      "ObservedProperty@iot.navigationLink": "../Datastreams(62892)/ObservedProperty"<br>
    }</span><br>
  ]</span><br>
}</div>

Returns Datastream entities associated with the given Sensor entity.

**Parameters**

*thingId:* The id of the Sensor entity.

*skip:* Indicate the number of records to be skiped from the begining of the returned list from the server.

*top:* Indicate the maximum number of records to be returned.

*expand:* Indicates the related entities to be represented inline. Its value is a comma seperated list of navigation property names (e.g. "parameter1, parameter2").

*select:* Indicates which propeties to be returned explicitly. Its value is a comma seperated list of navigation property names (e.g. "parameter1, parameter2")

*filter:* Allows clients to filter a collection of entities that are addressed by a request URL.

*orderby:* Specifies the order in which items are returned from the service. Its value is a comma seperated list of navigation property names (e.g. "parameter1, parameter2")

*count:* A boolean value that specifies whether the total count of items be returned along with the result or not.

**Returns**

An ArrayList of the requested Datastream objects.

Parameters | Type | Required
-------------- | -------------- | --------------
id | long | mandatory
skip | int | mandatory
top | int | mandatory
expand | string | mandatory
filter | string | mandatory
orderby | string | mandatory
count | boolean | mandatory


## getDatastreamsOfObservedProperty

```csharp

Service service = new Service("http://example.org/OGCSensorThings/v1.0");
ArrayList array = service.getDatastreamsOfObservedProperty(97241, 2, 1); 

//print to JSON string to console
foreach(Datastream item in array){
	//print the properties
  Console.out.WriteLine("ID: "+dt.id);
  Console.out.WriteLine("description: "+dt.description);
  Console.out.WriteLine("observationType: "+dt.observationType);
  Console.out.WriteLine("Result Time: "+dt.resultTime);
  Console.out.WriteLine("Phenonmenon Time: "+dt.phenomenonTime);
}

```
><button id="btn" onclick="show('#dtExample15')">Show Response</button><div id="dtExample15" class="exampleStyle" style="display: none;">
ID: 62892<br>
description: Sound.<br>
Observation Type: http://www.opengis.net/def/observationType/OGC-OM/2.0/OM_Measurement<br>
result time: 0001-01-01 12:00:00 AM<br>
Phenonmenon Time: 0001-01-01 12:00:00 AM<br></div>

Returns Datastream entities associated with the given ObservedProperty entity.

**Parameters**

*sensorId:* The id of the ObservedProperty entity.

*skip:* Indicate the number of records to be skiped from the begining of the returned list from the server.

*top:* Indicate the maximum number of records to be returned.

**Returns**

An ArrayList of the requested Datastream objects.

Parameters | Type | Required
-------------- | -------------- | --------------
id | long | mandatory
skip | int | mandatory
top | int | mandatory


## getDatastreamsOfObservedPropertyJSON

```csharp

Service service = new Service("http://example.org/OGCSensorThings/v1.0");
string json = service.getDatastreamsOfObservedPropertyJSON(97241, 5, 1,"","","","id",true); 

Console.out.WriteLine(json);

```
><button id="btn" onclick="show('#dtExample16')">Show Response</button><div id="dtExample16" class="exampleStyle" style="display: none;">
{<span class="textIndent"><br>
  "count": 1,<br>
  "value": [<br>
    {<span class="textIndent"><br>
      "unitOfMeasurement": {<span class="textIndent">
        "symbol": "lm3",<br>
        "name": "Lume3n",<br>
        "definition": "http://w3ww.qudt.org/qudt/owl/1.0.0/unit/Instances.html#Lumen"</span><br>
      },<br>
      "@iot.selfLink": "http://example.org/OGCSensorThings/v1.0/Datastreams(115584)",<br>
      "Thing@iot.navigationLink": "../Datastreams(115584)/Thing",<br>
      "Sensor@iot.navigationLink": "../Datastreams(115584)/Sensor",<br>
      "observationType": "http://www.opengis.net/def/observationType/OGC-OM/2.0/OM_Measurement",<br>
      "@iot.id": 115584,<br>
      "description": "Light exposure.",<br>
      "Observations@iot.navigationLink": "../Datastreams(115584)/Observations",<br>
      "ObservedProperty@iot.navigationLink": "../Datastreams(115584)/ObservedProperty"<br>
    }</span><br>
  ]<br>
}</div>

Returns Datastream entities associated with the given ObservedProperty entity.

**Parameters**

*thingId:* The id of the ObservedProperty entity.

*skip:* Indicate the number of records to be skiped from the begining of the returned list from the server.

*top:* Indicate the maximum number of records to be returned.

*expand:* Indicates the related entities to be represented inline. Its value is a comma seperated list of navigation property names (e.g. "parameter1, parameter2").

*select:* Indicates which propeties to be returned explicitly. Its value is a comma seperated list of navigation property names (e.g. "parameter1, parameter2")

*filter:* Allows clients to filter a collection of entities that are addressed by a request URL.

*orderby:* Specifies the order in which items are returned from the service. Its value is a comma seperated list of navigation property names (e.g. "parameter1, parameter2")

*count:* A boolean value that specifies whether the total count of items be returned along with the result or not.

**Returns**

An ArrayList of the requested Datastream objects.

Parameters | Type | Required
-------------- | -------------- | --------------
id | long | mandatory
skip | int | mandatory
top | int | mandatory
expand | string | mandatory
filter | string | mandatory
orderby | string | mandatory
count | boolean | mandatory


