---
title: SensorThings .NET Library Reference

language_tabs:
  - csharp: C#

toc_footers:
  - <a href='#'>Sign Up for a Developer Key</a>
  - <a href='http://github.com/tripit/slate'>Documentation Powered by Slate</a>

includes:
  - things
  - locations
  - historicallocations
  - datastreams
  - sensors
  - observedproperties
  - observations
  - featuresofinterest
  - supportivefunctions
  - errors

search: true
---

# Introduction

Welcome to the SensorThings .NET Library based on SensorThings API. This library allows clients to easily connect with the SensorThings API. This library allows clients to retrieve information that is parsed and can be used in their project. 

This document provides guidance for developers on how to use the library in their project. This documents shows how to retrieve specific information from each method. 

# Requirements

In order to use this library, the developer must have the following tools:

- .NET framework 4.5
- Microsoft Visual Studio 2013 (or later version). You can use the free Express version or you can use Xamarin (for MAC).
- The application should be written in C# language.

# Installation

> Add the following dependencies to your file:

```csharp

using OGCSensorThingsClassLibrary;
using Newtonsoft.Json;
using Newtonsoft;

```

In order to use this library, you must add it into your project. The following steps describe how to include the library: 

1. Start new C# Desktop or Web application in Visual Studio 2013 or Xamarin.
2. Right click on the References tab of your application, and then click Add Reference...
3. In the Reference Manager window, click on 'Browse', then navigate to:
OGCSensorThingsClassLibrary > OGCSensorThingsClassLibrary > bin/Debug
4. In the bin/Debug folder you will find two dll files: Newtonsoft.Json.dll and OGCSensorThingsClassLibrary.dll. Add both of them as new references. 
You can also add the Newtonsoft library by going to the package folder, right-click and select "add package", type in the search bar "newtonsoft", and add the first item to the project. 
5. Add the following in the top of each .cs file where you will use the library classes or methods:

# Methods

The following sections describe each method that is available for use in the library. It defines the parameters as well as the return types of each method. It also shows segments of code as well as a expected output. 




