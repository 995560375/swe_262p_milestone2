# MSWE 262P Project

## Milestone3
- In this project, we add a overload method at src/main/java/org.json/XML.java. The method signatures are as follows:
- public static JSONObject toJSONObject(Reader reader, Function<String, String> changeString)

- We have made modifications to the original parse function and renamed it to "parseAndModify". This change allows us to modify the key while parsing the XML file directly, unlike the original method, which requires parsing the XML file completely and converting it into a JsonObject before changing the key. The milestone1 approach requires traversing the file(json) twice, making it less time-efficient. However, with our modified parse function, we can accomplish the same task in a single traversal of the file, resulting in a more efficient solution.

## Milestone4
- In this project, we add two functions in src/main/java/org.json/JSONObject.java.
The two functions start at JSONObject.java line 2719. It converts a JSON object to a stream of JSON objects. The toStream() method builds a Stream.Builder and then calls the buildStream() method to add JSON objects to the builder based on the keys and values in the original JSON object.

- The Unit test start at JSONObjectTest.java line 3515. It tests the stream fuctions like filter, forEach, size and iteration.

## Milestone5
n milestone 5, we added an asynchronous method to the XML library with the following signature: public static Future<JSONObject> toJSONObjectMilestone5(Reader reader). 

You can find the code in XML.java and start from 1943 line, and test in the XMLtest.java starting from line162.

To implement this method asynchronously, we initialize an ExecutorService within the method and use the submit function to execute a task. The submit function can accept a Runnable or Callable instance, so we create a Callable class called Task. The submit function returns a Future object, which represents the pending result of the task. We can retrieve the result by calling the get() function of the Future interface. This asynchronous method allows us to perform other tasks while waiting for the JSONObject to become available.


![Json-Java logo](https://github.com/stleary/JSON-java/blob/master/images/JsonJava.png?raw=true)

<sub><sup>image credit: Ismael Pérez Ortiz</sup></sub>


JSON in Java [package org.json]
===============================

[![Maven Central](https://img.shields.io/maven-central/v/org.json/json.svg)](https://mvnrepository.com/artifact/org.json/json)

**[Click here if you just want the latest release jar file.](https://search.maven.org/remotecontent?filepath=org/json/json/20220924/json-20220924.jar)**


# Overview

[JSON](http://www.JSON.org/) is a light-weight language-independent data interchange format.

The JSON-Java package is a reference implementation that demonstrates how to parse JSON documents into Java objects and how to generate new JSON documents from the Java classes.

Project goals include:
* Reliable and consistent results
* Adherence to the JSON specification 
* Easy to build, use, and include in other projects
* No external dependencies
* Fast execution and low memory footprint
* Maintain backward compatibility
* Designed and tested to use on Java versions 1.6 - 1.11

The files in this package implement JSON encoders and decoders. The package can also convert between JSON and XML, HTTP headers, Cookies, and CDL.

# If you would like to contribute to this project

For more information on contributions, please see [CONTRIBUTING.md](https://github.com/stleary/JSON-java/blob/master/docs/CONTRIBUTING.md)

Bug fixes, code improvements, and unit test coverage changes are welcome! Because this project is currently in the maintenance phase, the kinds of changes that can be accepted are limited. For more information, please read the [FAQ](https://github.com/stleary/JSON-java/wiki/FAQ).

# Build Instructions

The org.json package can be built from the command line, Maven, and Gradle. The unit tests can be executed from Maven, Gradle, or individually in an IDE e.g. Eclipse.
 
**Building from the command line**

*Build the class files from the package root directory src/main/java*
````
javac org/json/*.java
````

*Create the jar file in the current directory*
````
jar cf json-java.jar org/json/*.class
````

*Compile a program that uses the jar (see example code below)*
````
javac -cp .;json-java.jar Test.java (Windows)
javac -cp .:json-java.jar Test.java (Unix Systems)
````

*Test file contents*

````
import org.json.JSONObject;
public class Test {
    public static void main(String args[]){
       JSONObject jo = new JSONObject("{ \"abc\" : \"def\" }");
       System.out.println(jo.toString());
    }
}
````

*Execute the Test file*
```` 
java -cp .;json-java.jar Test (Windows)
java -cp .:json-java.jar Test (Unix Systems)
````

*Expected output*

````
{"abc":"def"}
````

 
**Tools to build the package and execute the unit tests**

Execute the test suite with Maven:
```
mvn clean test
```

Execute the test suite with Gradlew:

```
gradlew clean build test
```

# Notes

For more information, please see [NOTES.md](https://github.com/stleary/JSON-java/blob/master/docs/NOTES.md)

# Files

For more information on files, please see [FILES.md](https://github.com/stleary/JSON-java/blob/master/docs/FILES.md)

# Release history:

For the release history, please see [RELEASES.md](https://github.com/stleary/JSON-java/blob/master/docs/RELEASES.md)
