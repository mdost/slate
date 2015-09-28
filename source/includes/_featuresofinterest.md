<script type="text/javascript" src="../javascripts/sensorup.js"></script>
<link rel="stylesheet" type="text/css" href="../stylesheets/sensorup.css">

# FeaturesOfInterest

## addNewFeatureOfInterest

```csharp
Service service = new Service ("http://example.org/OGCSensorThings/v1.0");
string response = service.addNewFeatureOfInterest ("current location of feature", "application/vnd.geo+json", "{\"coordinates\": [\"51.08374\",\"-114.13032\"],\"type\": \"Point\"}");
Console.Out.WriteLine(response);

```

><button id="btn" onclick="show('#foiExample1')">Show Response</button><div id="foiExample1" class="exampleStyle" style="display: none;">
{<span class="textIndent"><br>
  "@iot.selfLink":"http://example.org/OGCSensorThings/v1.0/FeaturesOfInterest(116113)",<br>
  "feature":{<span class="textIndent">
      "coordinates":["51.08374","-114.13032"],<br>
      "type":"Point"</span><br>
    },<br>
    "@iot.id":116113,<br>
    "encodingType":"application/vnd.geo+json",<br>
    "description":"current location of feature",<br>
    "Observations@iot.navigationLink":"../FeaturesOfInterest(116113)/Observations"</span><br>
}</div>

Create new FeatureOfInterest entity in OGC SensorThings database.

**Parameters**

*description:* A description of the FeatureOfInterest.

*encodingType:* The encoding type of the FeatureOfInterest entity.

*feature:* The feature of the FeatureOfInterest entity.

**Returns**

JSON string of the new FeatureOfInterest entity or error message if new record is not added.


Parameters | Type | Required
-------------- | -------------- | --------------
description | string | mandatory
encodingType | string | mandatory
feature | long | mandatory


## addNewFeatureOfInterestByJSON

```csharp
Service service = new Service ("http://example.org/OGCSensorThings/v1.0");
string jsonString="{ 
    \"description\": \"current location of feature\", 
    \"feature\": {
        \"coordinates\": [\"51.08374\",\"-114.13032\"],
        \"type\": \"Point\"
      },
      \"encodingType\": \"application/vnd.geo+json\"
    }";
      
string response = service.addNewFeatureOfInterestByJSON (jsonString);
Console.Out.WriteLine(response);

```

><button id="btn" onclick="show('#foiExample2')">Show Response</button><div id="foiExample2" class="exampleStyle" style="display: none;">
{<span class="textIndent"><br>
  "@iot.selfLink":"http://example.org/OGCSensorThings/v1.0/FeaturesOfInterest(116113)",<br>
  "feature":{<span class="textIndent">
      "coordinates":["51.08374","-114.13032"],<br>
      "type":"Point"</span><br>
    },<br>
    "@iot.id":116113,<br>
    "encodingType":"application/vnd.geo+json",<br>
    "description":"current location of feature",<br>
    "Observations@iot.navigationLink":"../FeaturesOfInterest(116113)/Observations"</span><br>
}</div>

Create new FeatureOfInterest entity in OGC SensorThings database.

**Parameters**

*jsonString:* A JSON string describing the new FeatureOfInterest entity to be created.

**Returns**

JSON string of the new FeatureOfInterest entity or Error message if new record is not added.


Parameters | Type | Required
-------------- | -------------- | --------------
jsonString | string | mandatory


## deleteFeatureOfInterest

```csharp

Service service = new Service ("http://example.org/OGCSensorThings/v1.0");
string response = service.deleteFeatureOfInterest (78895);

Console.Out.WriteLine(response);

```

><button id="btn" onclick="show('#foiExample3')">Show Response</button><div id="foiExample3" class="exampleStyle" style="display: none;">
Succeeded: Record is deleted</div>

Delete FeatureOfInterest entity from the OGC SensorThings database.

**Parameters**

*id:* The id of the FeatureOfInterest entity to be deleted.

**Returns**

String showing the status of the delete operation.

Parameters | Type | Required
-------------- | -------------- | --------------
id | long | mandatory




## getFeaturesOfInterest

```csharp

Service service = new Service("http://example.org/OGCSensorThings/v1.0");
ArrayList array = service.getFeaturesOfInterest(0, 1)		//return the first element

foreach(FeatureOfInterest item in array){
	//print the properties
	Console.out.WriteLine("ID: "+item.id);
	Console.out.WriteLine("description: "+item.description);
}

```
><button id="btn" onclick="show('#foiExample4')">Show Response</button><div id="foiExample4" class="exampleStyle" style="display: none;">
ID: 120217<br>
description: current location of feature</div>


Returns an ArrayList of FeatureOfInterest objects according to the specified skip and top values.

**Parameters**

*skip:* Indicate the number of records to be skiped from the begining of the returned list from the server.

*top:* Indicate the maximum number of records to be returned.

**Returns**

An ArrayList of FeatureOfInterest objects

Parameters | Type | Required
-------------- | -------------- | --------------
skip | int | mandatory
top | int | mandatory


## getFeaturesOfInterestJSON

```csharp

Service service = new Service("http://example.org/OGCSensorThings/v1.0");
string json = service.getFeaturesOfInterestJSON(3, 3, "","id","id gt 1000","id",false);	//skip the first three elements and return three element only displaying id, filter id's that are greater than 10000, order by id, and don't return the count. 

//print the json string to console
Console.out.WriteLine(json);

```
><button id="btn" onclick="show('#foiExample5')">Show Response</button><div id="foiExample5" class="exampleStyle" style="display: none;">
{<span class="textIndent"><br>
  "@iot.nextLink":"http://example.org/OGCSensorThings/v1.0/FeaturesOfInterest?$skip=6&$top=3&$expand=&$filter=id gt 1000&$orderby=id&$count=False&$select=id",<br>
  "value":[<span class="textIndent">
    {"id":5876},<br>
    {"id":14113},<br>
    {"id":14115}</span><br>
  ]</span><br>
}</div>


Returns a JSON string of FeatureOfInterest records according to the specified skip, top, expand, select, filter, orderby, and count values.

**Parameters**

*skip:* Indicate the number of records to be skiped from the begining of the returned list from the server.

*top:* Indicate the maximum number of records to be returned.

*expand:* Indicates the related entities to be represented inline. Its value is a comma seperated list of navigation property names (e.g. "parameter1, parameter2").

*select:* Indicates which propeties to be returned explicitly. Its value is a comma seperated list of navigation property names (e.g. "parameter1, parameter2")

*filter:* Allows clients to filter a collection of entities that are addressed by a request URL.

*orderby:* Specifies the order in which items are returned from the service. Its value is a comma seperated list of navigation property names (e.g. "parameter1, parameter2")

*count:* A boolean value that specifies whether the total count of items be returned along with the result or not.

**Returns**

A JSON string of the requested FeatureOfInterest records.

Parameters | Type | Required
-------------- | -------------- | --------------
skip | int | mandatory
top | int | mandatory
expand | string | mandatory
filter | string | mandatory
orderby | string | mandatory
count | boolean | mandatory

## getFeatureOfInterestById

```csharp

Service service = new Service("http://example.org/OGCSensorThings/v1.0");
FeatureOfInterest foi = service.getFeatureOfInterestById(78893); 

//print to console the properties of location
Console.out.WriteLine("ID: "+foi.id);
Console.out.WriteLine("description: "+foi.description);

```
><button id="btn" onclick="show('#foiExample6')">Show Response</button><div id="foiExample6" class="exampleStyle" style="display: none;">
ID: 78893 <br>
description: current location of feature<br>
</div>


Returns a FeatureOfInterest object of the given id parameter.

**Parameters**

*id:* The id of the requested FeatureOfInterest entity.

**Returns**

A FeatureOfInterest object

Parameters | Type | Required
-------------- | -------------- | --------------
id | long | mandatory


## getFeatureOfInterestByIdJSON

```csharp

Service service = new Service("http://example.org/OGCSensorThings/v1.0");
string json = service.getFeatureOfInterestByIdJSON(78893); 

//print to JSON string to console
Console.out.WriteLine(json);

```
><button id="btn" onclick="show('#foiExample7')">Show Response</button><div id="foiExample7" class="exampleStyle" style="display: none;">
{<span class="textIndent"><br>
  "@iot.selfLink": "http://example.org/OGCSensorThings/v1.0/FeaturesOfInterest(78893)",<br>
  "feature": {<span class="textIndent">
    "coordinates": ["51.08375","-114.13033"],<br>
    "type": "Point"</span><br>
  },<br>
  "@iot.id": 78893,<br>
  "encodingType": "application/vnd.geo+json",<br>
  "description": "current location of feature",<br>
  "Observations@iot.navigationLink": "../FeaturesOfInterest(78893)/Observations"</span><br>
}</div>


Returns a JSON string of the FeatureOfInterest record by the given id parameter.

**Parameters**

*id:* The id of the requested FeatureOfInterest entity.

**Returns**

A JSON string of the requested FeatureOfInterest entity

Parameters | Type | Required
-------------- | -------------- | --------------
id | long | mandatory
