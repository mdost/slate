<script type="text/javascript" src="../javascripts/sensorup.js"></script>
<link rel="stylesheet" type="text/css" href="../stylesheets/sensorup.css">

# Observations

## addNewObservation

```csharp
Service service = new Service ("http://example.org/OGCSensorThings/v1.0");
string response = service.addNewObservation ("419.432", "2015-09-22T14:35:00.000Z",115584, 9669964);

Console.Out.WriteLine(response);

```
><button id="btn" onclick="show('#observExample1')">Show Response</button><div id="observExample1" class="exampleStyle" style="display: none;">
{<span class="textIndent"><br>
  "result": "419.432",<br>
  "resultTime": null,<br>
  "@iot.selfLink": "http://example.org/OGCSensorThings/v1.0/Observations(9869515)",<br>
  "@iot.id": 9869515,<br>
  "phenomenonTime": "2015-09-22T14:35:00.000Z",<br>
  "FeatureOfInterest@iot.navigationLink": "../Observations(9869515)/FeatureOfInterest",<br>
  "Datastream@iot.navigationLink": "../Observations(9869515)/Datastream"</span><br>
}</div>

Create new Datastream entity in OGC SensorThings database.

**Parameters**

*result:* The result of the Observation entity.

*phenomenonTime:* The phenomenon time of the observation.

*datastreamID:* The id of the Datastream to be associated with the new Observation entity.

*featureOfInterestID:* The id of the FeatureOfInterest to be associated with the new Observation entity.


**Returns**

JSON string of the new Observation entity or error message if new record is not added.


Parameters | Type | Required
-------------- | -------------- | --------------
result | string | mandatory
phenomenonTime | string | mandatory
datastreamID | long | mandatory
featureOfInterestID | long | optional


## addNewObservationByJSON

```csharp
Service service = new Service ("http://example.org/OGCSensorThings/v1.0");
string jsonString="{
    \"result\": \"thermostate of the home office\", 
    \"phenomenonTime\": \"2015-09-22T14:35:00.000Z\", 
    \"Datastream\":{\"@iot.id\":  115584 },
    \"FeatureOfInterest\":{\"@iot.id\": 9669964}
  }";

string response = service.addNewObservation (jsonString);

Console.Out.WriteLine(response);
```
><button id="btn" onclick="show('#observExample2')">Show Response</button><div id="observExample2" class="exampleStyle" style="display: none;">
{<span class="textIndent"><br>
  "result": "419.432",<br>
  "resultTime": null,<br>
  "@iot.selfLink": "http://example.org/OGCSensorThings/v1.0/Observations(9869515)",<br>
  "@iot.id": 9869515,<br>
  "phenomenonTime": "2015-09-22T14:35:00.000Z",<br>
  "FeatureOfInterest@iot.navigationLink": "../Observations(9869515)/FeatureOfInterest",<br>
  "Datastream@iot.navigationLink": "../Observations(9869515)/Datastream"</span><br>
}</div>

Create new Observation entity in OGC SensorThings database.

**Parameters**

*jsonString:* A JSON string describing the new Observation entity to be created.


**Returns**

JSON string of the new Observation entity or error message if new record is not added.


Parameters | Type | Required
-------------- | -------------- | --------------
jsonString | string | mandatory


## deleteObservation

```csharp
Service service = new Service ("http://example.org/OGCSensorThings/v1.0");
string response = service.deleteObservation (62674);

Console.Out.WriteLine(response);

```
><button id="btn" onclick="show('#observExample3')">Show Response</button><div id="observExample3" class="exampleStyle" style="display: none;">
Succeeded: Record is deleted</div>

Delete Observation entity from the OGC SensorThings database.

**Parameters**

*id:* The id of the Observation entity to be deleted.

**Returns**

String showing the status of the delete operation.

Parameters | Type | Required
-------------- | -------------- | --------------
id | long | mandatory


## getObservations

```csharp
Service service = new Service("http://example.org/OGCSensorThings/v1.0");
ArrayList array = service.getObservations(0, 2)		//return the first element

foreach(Observation item in array){
	//print the properties
	Console.out.WriteLine("ID: "+item.id);
	Console.out.WriteLine("Result: "+item.result);
}
```
><button id="btn" onclick="show('#observExample4')">Show Response</button><div id="observExample4" class="exampleStyle" style="display: none;">
ID: 9869515 <br>
Result: 419.432<br>
ID: 9870810 <br>
Result: 1.188<br>
</div>

Returns an ArrayList of Observation objects according to the specified skip and top values.

**Parameters**

*skip:* Indicate the number of records to be skiped from the begining of the returned list from the server.

*top:* Indicate the maximum number of records to be returned.

**Returns**

An ArrayList of Observation objects

Parameters | Type | Required
-------------- | -------------- | --------------
skip | int | mandatory
top | int | mandatory


## getObservationsJSON

```csharp

Service service = new Service("http://example.org/OGCSensorThings/v1.0");
string json = service.getObservationsJSON(10, 2, "","","","",false);		//skip the first ten elements and return two elements only displaying id, and don't return the count. 

//print the json string to console
Console.out.WriteLine(json);

```
><button id="btn" onclick="show('#observExample5')">Show Response</button><div id="observExample5" class="exampleStyle" style="display: none;">
{<span class="textIndent"><br>
  "@iot.nextLink":"http://example.org/OGCSensorThings/v1.0/Things?$skip=10&$top=2&$expand=&$filter=&$orderby=&$count=False",<br>
  "value":[
  {<span class="textIndent">
      "result": "4.038",<br>
      "resultTime": null,<br>
      "@iot.selfLink": "http://example.org/OGCSensorThings/v1.0/Observations(9871622)",<br>
      "@iot.id": 9871622,<br>
      "phenomenonTime": "2015-09-22T14:20:00.000Z",<br>
      "FeatureOfInterest@iot.navigationLink": "../Observations(9871622)/FeatureOfInterest",<br>
      "Datastream@iot.navigationLink": "../Observations(9871622)/Datastream"</span><br>
    },<br>
    {<span class="textIndent">
      "result": "1.984",<br>
      "resultTime": null,<br>
      "@iot.selfLink": "http://example.org/OGCSensorThings/v1.0/Observations(9869688)",<br>
      "@iot.id": 9869688,<br>
      "phenomenonTime": "2015-09-22T14:20:00.000Z",<br>
      "FeatureOfInterest@iot.navigationLink": "../Observations(9869688)/FeatureOfInterest",<br>
      "Datastream@iot.navigationLink": "../Observations(9869688)/Datastream"</span><br>
    }]</span><br>
}</div>

Returns a JSON string of Observation records according to the specified skip, top, expand, select, filter, orderby, and count values.

**Parameters**

*skip:* Indicate the number of records to be skiped from the begining of the returned list from the server.

*top:* Indicate the maximum number of records to be returned.

*expand:* Indicates the related entities to be represented inline. Its value is a comma seperated list of navigation property names (e.g. "parameter1, parameter2").

*select:* Indicates which propeties to be returned explicitly. Its value is a comma seperated list of navigation property names (e.g. "parameter1, parameter2")

*filter:* Allows clients to filter a collection of entities that are addressed by a request URL.

*orderby:* Specifies the order in which items are returned from the service. Its value is a comma seperated list of navigation property names (e.g. "parameter1, parameter2")

*count:* A boolean value that specifies whether the total count of items be returned along with the result or not.

**Returns**

A JSON string of the requested Observation records.

Parameters | Type | Required
-------------- | -------------- | --------------
skip | int | mandatory
top | int | mandatory
expand | string | mandatory
filter | string | mandatory
orderby | string | mandatory
count | boolean | mandatory

## getObservationById

```csharp

Service service = new Service("http://example.org/OGCSensorThings/v1.0");
Observation observation = service.getObservationById(9871622); 

//print to console the properties of location
Console.out.WriteLine("ID: "+observation.id);
Console.out.WriteLine("Result: "+observation.result);

```
><button id="btn" onclick="show('#observExample6')">Show Response</button><div id="observExample6" class="exampleStyle" style="display: none;">
ID: 9871622<br>
Result: 4.038<br>
</div>

Returns a Observation object of the given id parameter.

**Parameters**

*id:* The id of the requested Observation entity.

**Returns**

A Observation object

Parameters | Type | Required
-------------- | -------------- | --------------
id | long | mandatory


## getObservationByIdJSON

```csharp

Service service = new Service("http://example.org/OGCSensorThings/v1.0");
string json = service.getObservationByIdJSON(9871622); 

//print to JSON string to console
Console.out.WriteLine(json);

```
><button id="btn" onclick="show('#observExample7')">Show Response</button><div id="observExample7" class="exampleStyle" style="display: none;">
{<span class="textIndent"><br>
  "result": "4.038",<br>
  "resultTime": null,<br>
  "@iot.selfLink": "http://example.org/OGCSensorThings/v1.0/Observations(9871622)",<br>
  "@iot.id": 9871622,<br>
  "phenomenonTime": "2015-09-22T14:20:00.000Z",<br>
  "FeatureOfInterest@iot.navigationLink": "../Observations(9871622)/FeatureOfInterest",<br>
  "Datastream@iot.navigationLink": "../Observations(9871622)/Datastream"</span><br>
}</div>

Returns a JSON string of the Observation record by the given id parameter.

**Parameters**

*id:* The id of the requested Observation entity.

**Returns**

A JSON string of the requested Observation entity

Parameters | Type | Required
-------------- | -------------- | --------------
id | long | mandatory


## getObservationsOfDatastream

```csharp

Service service = new Service("http://example.org/OGCSensorThings/v1.0");
ArrayList array = service.getObservationsOfDatastream(58966, 0, 1); 

//print to JSON string to console
foreach(Observation item in array){
	//print the properties
	Console.out.WriteLine(item.id);
	Console.out.WriteLine(item.result);
}

```
><button id="btn" onclick="show('#observExample8')">Show Response</button><div id="observExample8" class="exampleStyle" style="display: none;">
ID: 9855921<br>
Result: 0.585<br>
</div>

Returns Observation entities associated with the given Datastream entity.

**Parameters**

*datastreamId:* The id of the Datastream entity.

*skip:* Indicate the number of records to be skiped from the begining of the returned list from the server.

*top:* Indicate the maximum number of records to be returned.

**Returns**

An ArrayList of the requested Observation objects.

Parameters | Type | Required
-------------- | -------------- | --------------
id | long | mandatory
skip | int | mandatory
top | int | mandatory

## getObservationsOfDatastreamJSON

```csharp

Service service = new Service("http://example.org/OGCSensorThings/v1.0");
string json = service.getObservationsOfDatastreamJSON(58966,0, 1,"","","","id",true); 

Console.out.WriteLine(json);

```
><button id="btn" onclick="show('#observExample9')">Show Response</button><div id="observExample9" class="exampleStyle" style="display: none;">
{<span class="textIndent"><br>
  "@iot.nextLink":"http://example.org/OGCSensorThings/v1.0/Things?$skip=0&$top=1&$expand=&$filter=&$orderby=id&$count=True",<br>
  "count":1,<br>
  "value":[<br>
    {<span class="textIndent">
      "result": "1.866",<br>
      "resultTime": null,<br>
      "@iot.selfLink": "http://example.org/OGCSensorThings/v1.0/Observations(9869336)",<br>
      "@iot.id": 9869336,<br>
      "phenomenonTime": "2015-09-22T14:15:00.000Z",<br>
      "FeatureOfInterest@iot.navigationLink": "../Observations(9869336)/FeatureOfInterest",<br>
      "Datastream@iot.navigationLink": "../Observations(9869336)/Datastream"</span><br>
    }]<br>
}</div>

Returns Observation entities associated with the given Datastream entity.

**Parameters**

*datastreamId:* The id of the Datastream entity.

*skip:* Indicate the number of records to be skiped from the begining of the returned list from the server.

*top:* Indicate the maximum number of records to be returned.

*expand:* Indicates the related entities to be represented inline. Its value is a comma seperated list of navigation property names (e.g. "parameter1, parameter2").

*select:* Indicates which propeties to be returned explicitly. Its value is a comma seperated list of navigation property names (e.g. "parameter1, parameter2")

*filter:* Allows clients to filter a collection of entities that are addressed by a request URL.

*orderby:* Specifies the order in which items are returned from the service. Its value is a comma seperated list of navigation property names (e.g. "parameter1, parameter2")

*count:* A boolean value that specifies whether the total count of items be returned along with the result or not.

**Returns**

An ArrayList of the requested Observation objects.

Parameters | Type | Required
-------------- | -------------- | --------------
id | long | mandatory
skip | int | mandatory
top | int | mandatory
expand | string | mandatory
filter | string | mandatory
orderby | string | mandatory
count | boolean | mandatory


## getObservationsOfFeatureOfInterest

```csharp

Service service = new Service("http://example.org/OGCSensorThings/v1.0");
ArrayList array = service.getObservationsOfFeatureOfInterest(9414952, 0, 2); 

//print to JSON string to console
foreach(Datastream item in array){
	//print the properties
	Console.out.WriteLine(item.id);
	Console.out.WriteLine(item.observationType);
}

```
><button id="btn" onclick="show('#observExample10')">Show Response</button><div id="observExample10" class="exampleStyle" style="display: none;">
ID: 9767398 <br>
Result: 223.744<br>
ID: 9782230<br>
Result: 335.812<br>
</div>

Returns Observation entities associated with the given FeatureOfInterest entity.

**Parameters**

*featureOfInterestId:* The id of the FeatureOfInterest entity.

*skip:* Indicate the number of records to be skiped from the begining of the returned list from the server.

*top:* Indicate the maximum number of records to be returned.

**Returns**

An ArrayList of the requested Observation objects.

Parameters | Type | Required
-------------- | -------------- | --------------
id | long | mandatory
skip | int | mandatory
top | int | mandatory


## getObservationsOfFeatureOfInterestJSON

```csharp

Service service = new Service("http://example.org/OGCSensorThings/v1.0");
string json = service.getObservationsOfFeatureOfInterestJSON(9414952, 5, 2,"","","","id",true); 

Console.out.WriteLine(json);

```
><button id="btn" onclick="show('#observExample11')">Show Response</button><div id="observExample11" class="exampleStyle" style="display: none;">
{<span class="textIndent"><br>
  "@iot.nextLink":"http://example.org/OGCSensorThings/v1.0/Things?$skip=5&$top=2&$expand=&$filter=&$orderby=id&$count=True",<br>
  "count":1,<br>
  "value":[<br>
    {<span class="textIndent">
      "result": "1.866",<br>
      "resultTime": null,<br>
      "@iot.selfLink": "http://example.org/OGCSensorThings/v1.0/Observations(9869332)",<br>
      "@iot.id": 9869332,<br>
      "phenomenonTime": "2015-09-22T13:55:00.000Z",<br>
      "FeatureOfInterest@iot.navigationLink": "../Observations(9869332)/FeatureOfInterest",<br>
      "Datastream@iot.navigationLink": "../Observations(9869332)/Datastream"<br></span>
    },<br>
    {<span class="textIndent">
      "result": "4.035",<br>
      "resultTime": null,<br>
      "@iot.selfLink": "http://example.org/OGCSensorThings/v1.0/Observations(9871617)",<br>
      "@iot.id": 9871617,<br>
      "phenomenonTime": "2015-09-22T13:55:00.000Z",<br>
      "FeatureOfInterest@iot.navigationLink": "../Observations(9871617)/FeatureOfInterest",<br>
      "Datastream@iot.navigationLink": "../Observations(9871617)/Datastream"<br></span>
    }]<br>
}</div>

Returns Observation entities associated with the given FeatureOfInterest entity.

**Parameters**

*featureOfInterestId:* The id of the FeatureOfInterest entity.

*skip:* Indicate the number of records to be skiped from the begining of the returned list from the server.

*top:* Indicate the maximum number of records to be returned.

*expand:* Indicates the related entities to be represented inline. Its value is a comma seperated list of navigation property names (e.g. "parameter1, parameter2").

*select:* Indicates which propeties to be returned explicitly. Its value is a comma seperated list of navigation property names (e.g. "parameter1, parameter2")

*filter:* Allows clients to filter a collection of entities that are addressed by a request URL.

*orderby:* Specifies the order in which items are returned from the service. Its value is a comma seperated list of navigation property names (e.g. "parameter1, parameter2")

*count:* A boolean value that specifies whether the total count of items be returned along with the result or not.

**Returns**

An ArrayList of the requested Observation objects.

Parameters | Type | Required
-------------- | -------------- | --------------
id | long | mandatory
skip | int | mandatory
top | int | mandatory
expand | string | mandatory
filter | string | mandatory
orderby | string | mandatory
count | boolean | mandatory
