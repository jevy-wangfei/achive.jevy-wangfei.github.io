---
layout: default
title: Telecom Business Data Process
dd: TelecomBusinessDataProcess
category: timeline
tags: project
quote: The Telecom Business Data Process aims to analysis large scale telecom data in easy way.
---

#Telecom Business Intelligence#

##Objective
Telecom company manages millions subscribers and the subscribers generate billions calling and surfing internet records. With the increase of records, finding useful information becomes a challenge.
This project will go to find/lean new pattern from the large volume of data by applying Machine Leaning technology. <br/>
Targets include:
- Subscriber fraud detection
- Valuable subscribers finding
- Telecom Services using trend analysis
- Business decision data preparing

##Why Focus on Telecom business data
- Telecom data volume is not small and not very big.
  The data volume of telecom is roughly TB per month. Perform any query to the records will very compute resource consuming. Analysis staffs can not execute SQL to find useful information. Big data tools (such as Hadoop) are too general and complex for telecom companies to apply them into activating business operation.
- Telecom generates stream data
  Different with large scale batch data processing technology, telecom data is stream data and continuing lean technology is required.
- This project will go to explore new methods to process TB/month volume stream data using distributed data processing tools.
- This project will focus on new pattern finding in easy to use way for telecom companies. The vision is that normal office staffs can view and operate the intelligent data learning system without additional training of large scale data analysis.  

##Problems in Telecom Data
- Data volume is TB per month.
- Data analysis is needed every day.
- General data analysis tools are not specifically developed for telecom data analysis. Such that they require experienced staff in telecom data analysis.
- Lack of Data Analysis Expertise in telecom company.
- General data analysis tools either processing TB data per day or GB data per month. They are not suitable for medium scale data process.
- Telecom data analysis requires online and ongoing update analysis, since the subscribers generate data on time and these data are related from past to future.
- Technology invests limitation to develop a new Data analysis tool.

##Solution for Telecom Data
Three layer artecher: Leaning engine, Leaning system management & accessing application and User Interface (Explorer, Taplet, iOS, Android)
- Learning Engine Features (Spark + Hadoop)
  - Distributed computing network based
  - Steam data leaning support
  - Ongoing update leaning model
  - Learn status and result stores in NoSQL database
  - Telecom Customized learning models
    - Fraud Detection
    - Individual subscriber's habit leaning
    - Over view of service trends for groups
    - other models which can be extended

  **Technique for learning engine**

  Our solution is to use Hadoop as distributed computing framework, use Spark and its machine learning library as leaning learning engine, which runs on Hadoop.
- System Management & Accessing Features(JavaEE + Jersey + Tomcat8)
  - An united Management middleware will be designed to manage
    - creating new leaning task
    - checking on going leaning task
    - querying finished leaning task and returning leaning results
  - RESTful API will be well designed to make system friendly to kinds of user devices.

  **Technique for web application**

  Using tomcat as web application server, using javaEE and Jersey to program RESTful TelecomBI management and accessing application.
- User Interface Features (JS (Jquery) + HTML&CSS + Bootstrap)
  - Using RESTful style accessing API to create user interface on multi-devices such as explorer, iOS, Android.

  **Technique for client**

  Using HTML&CSS + Bootstrap to create user interface, Using JS accompanied with JQuery to query data from RESTful API server.

## Project Management
- Development Stages
  - Requirements survey and research
  - Project planning
  - System design
  - Develop and test loop:
    - System Implementation
    - System Testing
    - System Integration and Test
  - Publish System

## Technology Required

| Technology | Purpose |
|:--:|:---|
|Java Programming| Implement TelecomBI Server. </br> Implement Learning Engine|
|Scala Programming| Implement Learning Engine|
|Jersey| Implement Java RESTful web application|
|Java EE| Implement Java web application|
|Tomcat| Launch Jave Web Application|
|Hadoop| Implement Distributed computing framework|
|Spark| Implement Stream Data processing|
|Machine Leaning| Implement TelecomBI core learning Engin Algorithms|
|HTML&CSS| Implement user interface|
|Bootstrap| Improve user interface and simplify UI development|
|JS (JQuery)| Implement data query from web servers by RESTful API|
|Maven| Help to manage Java projects (Three projects)|
|Github| Help to manage code and team development|

## Required open soursce project

| Project | version|
|:--:|:---|
|[Spark](http://spark.apache.org)|1.4|
|[Hadoop]()|2.6|
|[Jersey]()|2.19|
|[Tomcat]()|8.0|
|Java|8.0|
|Scala|2.11.7|
|[Bootstrap]()|3.3.5|
|[JQuery]()|2.1.4|
|HTML&CSS| 5|
|[Maven]()|3.3.3|
|[Eclipse](eclipse.apache.org)|4.5|
