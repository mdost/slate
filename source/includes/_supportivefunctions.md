<script type="text/javascript" src="../javascripts/sensorup.js"></script>
<link rel="stylesheet" type="text/css" href="../stylesheets/sensorup.css">

# Supportive Methods

## getJson

```csharp

Service service = new Service("http://example.org/OGCSensorThings/v1.0");
string response = service.getJson ("http://example.org/OGCSensorThings/v1.0/Things?$top=1");

Console.out.WriteLine(response);

```

><button id="btn" onclick="show('#sfexample1')">Show Response</button><div id="sfexample1" class="exampleStyle" style="display: none;">
{<span class="textIndent"><br>
  "@iot.nextLink":"http://example.org/OGCSensorThings/v1.0/Things?$top=1&$skip=1",<br>
  "count":696,<br>
  "value":[<br>
    {<span class="textIndent">
      "@iot.selfLink":"http://example.org/OGCSensorThings/v1.0/Things(116355)",<br>
      "Datastreams@iot.navigationLink":"../Things(116355)/Datastreams",<br>
      "@iot.id":116355,<br>
      "description":"Thermostate of the house",<br>
      "Locations@iot.navigationLink":"../Things(116355)/Locations",<br>
      "properties":{<span class="textIndent">
          "material":"plastic"</span><br>
        },<br>
      "HistoricalLocations@iot.navigationLink":"../Things(116355)/HistoricalLocations"</span><br>
    }]</span><br>
}</div>

Returns the requested IoT entities specified by the given URL.

**Parameters**

*URL:* A URL string specifying the enetities to be returned.

**Returns**

JSON string representing the returned entities.

Parameters | Type | Required
-------------- | -------------- | --------------
URL | string | mandatory


## addRecord

```csharp

Service service = new Service("http://example.org/OGCSensorThings/v1.0");
string jsonString="{
        \"description\": \"thermostate of the home office\", 
        \"properties\": {\"color:\": \"green\"}, 
        \"Locations\":[{\"@iot.id\":  53416 }]}
    }";
string response = service.addRecord ("http://example.org/OGCSensorThings/v1.0/Things",jsonString);

Console.out.WriteLine(response);

```
><button id="btn" onclick="show('#sfexample2')">Show Response</button><div id="sfexample2" class="exampleStyle" style="display: none;">
{<span class="textIndent"><br>
  "@iot.selfLink":"http://example.org/OGCSensorThings/v1.0/Things(120101)",<br>
  "Datastreams@iot.navigationLink":"../Things(120101)/Datastreams",<br>
  "@iot.id":120101,<br>
  "description":"thermostate of the home office",<br>
  "Locations@iot.navigationLink":"../Things(120101)/Locations",<br>
  "properties":{<span class="textIndent">
      "color:":"green"</span><br>
    },<br>
  "HistoricalLocations@iot.navigationLink":"../Things(120101)/HistoricalLocations"<br>
}</div>


Create new entity in the OGC SensorThings database.

**Parameters**

*URL:* String specifying the entity type of the new record.

*json:* JSON string describing the new record to be added.

**Returns**

The status of the new record being added.

Parameters | Type | Required
-------------- | -------------- | --------------
URL | string | mandatory
json | string | mandatory

## updateRecord

```csharp

Service service = new Service("http://example.org/OGCSensorThings/v1.0");
string json = "{\"description\": \"thermostate of the building\"}";
string response = service.addRecord ("http://example.org/OGCSensorThings/v1.0/Things(120101)",json);

Console.out.WriteLine(json);

```
><button id="btn" onclick="show('#sfexample3')">Show Response</button><div id="sfexample3" class="exampleStyle" style="display: none;">
{<span class="textIndent"><br>
  "@iot.selfLink":"http://example.org/OGCSensorThings/v1.0/Things(120101)",<br>
  "Datastreams@iot.navigationLink":"../Things(120101)/Datastreams",<br>
  "@iot.id":120101,<br>
  "description":"thermostate of the building",<br>
  "Locations@iot.navigationLink":"../Things(120101)/Locations",<br>
  "properties":{<span class="textIndent">
      "color:":"green"</span><br>
    },<br>
  "HistoricalLocations@iot.navigationLink":"../Things(120101)/HistoricalLocations"<br>
}</div>

Update the content of an entity.

**Parameters**

*URL:* String specifying the entity to be updated.

*json:* JSON string describing the record to be updated.

**Returns**

The status showing the updated record.

Parameters | Type | Required
-------------- | -------------- | --------------
URL | string | mandatory
json | string | mandatory


## deleteRecord

```csharp

Service service = new Service("http://example.org/OGCSensorThings/v1.0");
string response = service.deleteRecord ("http://example.org/OGCSensorThings/v1.0/Things(120101)");

Console.out.WriteLine(response);

```
><button id="btn" onclick="show('#sfexample4')">Show Response</button><div id="sfexample4" class="exampleStyle" style="display: none;">
Succeeded: Record is deleted</div>

Delete entity from the OGC SensorThings database.

**Parameters**

*URL:* A URL string specifying the enetity to be deleted

**Returns**

string showing the deleted status

Parameters | Type | Required
-------------- | -------------- | --------------
URL | string | mandatory
