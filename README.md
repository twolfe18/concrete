Copyright 2012-2013 Johns Hopkins University HLTCOE. All rights reserved.
This software is released under the 2-clause BSD license.
See LICENSE in the project root directory.

//////////////////////////////////////////////////////////////////////////////
1. Introduction

Rebar protocol buffers are an attempt to map out various NLP data types in a 
protocol buffer schema for use in projects across Johns Hopkins University. 
This standardized schema allows researchers to use a common, underlying data
model for all NLP tasks, and thus, facilitating integration between projects.

//////////////////////////////////////////////////////////////////////////////
2. Requirements

Rebar protocol buffers (RPB) require the following:
* Java, 1.6 or greater
* Maven, 3.0.4 or greater
* Google protocol buffers, v. 2.4.1
  https://code.google.com/p/protobuf/
* Maven Protocol buffer plugin: 
  https://github.com/maxthomas/maven-protoc-plugin

//////////////////////////////////////////////////////////////////////////////
3. Installation

Once you have installed all required software, edit pom.xml and change the
protoc.location property to point to the location where you have installed
the protoc exectuable (e.g., /usr/lib/protoc). Alternatively, you can pass
in the property on the command line when invoking mvn, e.g., 

mvn install -Dprotoc.location=/usr/lib/protoc

In either case, running 

mvn install

will install the plugin to your local repository.

//////////////////////////////////////////////////////////////////////////////
4. Adding to your project

This plugin creates compiled Java classes that reflect our protocol buffer
definitions. You can use these in your java code by adding the following
dependency to your project's pom.xml file, once installed or deployed:

    <dependency>
      <groupId>edu.jhu.rebar</groupId>
      <artifactId>rebar-protobufs</artifactId>
      <version>1.0.0</version>
    </dependency>

At this time, we do not have this hosted on a public maven server. 

//////////////////////////////////////////////////////////////////////////////
5. Using the code in your project

Compiled java classes end up in the edu.jhu.rebar package. The protocol
buffers generate many classes; additional technical documentation can be found
in the comments of the protocol buffer definitions themselves.
