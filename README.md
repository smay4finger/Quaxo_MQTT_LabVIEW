Quaxo: MQTT for  LabVIEW
========================

A native LabVIEW MQTT client 

Overview
--------

MQTT (Message Queue Telemetry Transport) is a lightweight TCP-based messaging protocol targeting M2M applications, monitoring and distributed IO applications. It allows high latency and/or constrained networks, typically found in such applications.

The goal is to target any embedded RIO device for such applications.

The current version of the MQTT specification is 3.1. The specification can be found here: http://www.ibm.com/developerworks/webservices/library/ws-mqtt/index.html

Description
-----------

The MQTT infrastructure uses a Broker (server) to host "topics". Topics are of a hierarchical nature and can be named in a "URI" fashion: e.g. "SolarPlant1/Sensors/IrradiationSensor1“ to identify a specific data source. Clients can subscribe to topics and will receive updates when topics are updated from other clients (or servers). If they want to publish new data to topics, they can do so. There are different "Quality of Service" levels, allowing lossless or lossy transport, respectively. 

From the mqtt web site:

    The publish/subscribe message pattern to provide one-to-many message distribution and decoupling of applications
    A messaging transport that is agnostic to the content of the payload
    The use of TCP/IP to provide basic network connectivity
    Three qualities of service for message delivery:
        "At most once", where messages are delivered according to the best efforts of the underlying TCP/IP network. Message loss or duplication can occur. This level could be used, for example, with ambient sensor data where it does not matter if an individual reading is lost as the next one will be published soon after.
        "At least once", where messages are assured to arrive but duplicates may occur.
        "Exactly once", where message are assured to arrive exactly once. This level could be used, for example, with billing systems where duplicate or lost messages could lead to incorrect charges being applied.
    A small transport overhead (the fixed-length header is just 2 bytes), and protocol exchanges minimised to reduce network traffic
    A mechanism to notify interested parties to an abnormal disconnection of a client using the Last Will and Testament feature

 

 

Steps to Implement or Execute Code
----------------------------------

* Get  a broker server. E.g. "Mosquitto" or "RSMB". There are also public broker servers available, please see http://mqtt.org/wiki/doku.php/public_brokers
* Start the example VIs. In the example folders, "Simple connect and publish" will publish a string with a time stamp to a specific topic. "Simple connect and subscribe" let's your client VI subscribe to a number of topics. 

 

Requirements
------------
Software:
LabVIEW 2012

Hardware:
any platform you can program with LabVIEW that supports TCP/IP

Current status and what needs to be done
----------------------------------------
Currently, you should be able to get basic functionality for publishing and subscribing up and running quickly. However, some things are buggy and need to be tested.

Array operations are not optimized for embedded systems

And, if you're wondering - "Quaxo" is our code name for the project


Feel free to modify and improve the code! Please post it here, though!
