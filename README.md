# Smart City Data Streaming and Analytics 

***CS 6381: Distributed Systems | Spring 2018 | Vanderbilt University***

This project aims to provide an architecture for management and real-time analysis of sensor data collected from homes in a smart city. We demonstrate these key concepts of data collection, streaming, data management and analytics, with an overall goal to provide a reliable, secure and robust infrastructure for building a 'smart' community.

***Building Blocks***

a) Data Collection: Refers to the sensing stage, where sensors accumulate data. 

b) Data Streaming: Refers to the stage where, the sensed data is transported/ streamed to a data storage, which can be run on the local machine/ cloud.

c) Data Management: This refers to the database stage, where the streamed data is going to be stored.

d) Data Analytics: Performing query/ anomaly detection on the data to provide some data related feedback to the user.

e) Computing Paradigm: The main focus of this work is to focus on different computing paradigms of cloud/edge/Fog. 

***Architecture Challenges***

The proposed architecture should satisfy the following requirements:
a) Location transparency: The servers running the instance of database, should be migratable and available at any location.
b) Data protection: Data should be encrypted while being moved to the server.
c) Reliability: Any part of the architecture can break down, we need to think about making the system reliable and available.
d) Online Query: We should be able to perform some online query on the data using stream processing/ Complex Event Processing.
e) Plug and play. The architecture should be modular. The system should be able to integrateany new component without much of a problem.

The figure below shows the overall architecture of the smart city, which includes two main parts:

a) Smart home data streaming.

b) Air quality data monitoring.

![architecture v1.0](https://github.com/Shreyasramakrishna90/CS-6381-01-Final-Project/blob/master/images/smart-city.png)

***Different computing paradigms***

a) Cloud computing: Amazon EC2 instance.

b) Community Cloud: P2P digital ecosystem.

c) Fog computing: Servers maintained in the community.

***Smart home Data streaming***

The figure below shows in depth architecture and the actors involved in building a smart home data streming architecture. 
![architecture v1.0](https://github.com/Shreyasramakrishna90/CS-6381-01-Final-Project/blob/master/images/original_idea.png)

***Implementation***

a) We have a naive implementation of smart home data streaming and management.

b) Data is collected from my home using Aeotec multisensor, which uses openZwave library.

c) This data is streamed from homes using secured zmq transportation. We have used zmq stonehouse encryption method.

d) This data is transported to an Amazon EC2 instance where InfluxDB instance is running.

e) Query to display the data, grafana to plot the realtime data ingest.

***Scripts***

main.py: This collects the data from aeotec multisensor which uses python-openzwave library. This also has pub-sub zmq model to publish data to InfluxDB instance.
Influx.py: This starts InfluxDb instance Amazon EC2 instance.

***Results***

The figure below shows the realtime data being stored in the InfluxDB instance. The Aeotec multisensor6 reads luminance, tempearture, humidity, motion sensor, ultraviolet. These values are being recorede in the database as shown.
![architecture v1.0](https://github.com/Shreyasramakrishna90/CS-6381-01-Final-Project/blob/master/images/influxdata.png)

The data being written in the database, is plotted using grafana.
![architecture v1.0](https://github.com/Shreyasramakrishna90/CS-6381-01-Final-Project/blob/master/images/graph.png)

***Architectural challenges***

a) Data aggregation from homes to provide privacy.
![architecture v1.0](https://github.com/Shreyasramakrishna90/CS-6381-01-Final-Project/blob/master/images/distributed_homes.png)

b) Secured access of data so that the home data maintains privacy/ security.
![architecture v1.0](https://github.com/Shreyasramakrishna90/CS-6381-01-Final-Project/blob/master/images/security.jpg)
