﻿<properties linkid="develop-dotnet-intro-to-hadoop" urlDisplayName="Intro to Hadoop" pageTitle="Intro to Hadoop (.NET) - Windows Azure tutorials" metaKeywords="Azure Hadoop introduction, Hadoop Azure basics, intro Azure Hadoop" metaDescription="Learn about using Hadoop on Windows Azure." metaCanonical="" disqusComments="1" umbracoNaviHide="1" />




# Introduction to Hadoop on Windows Azure
**Overview**	
Apache™ Hadoop™-based Services for Windows Azure is a service that deploys and provisions clusters in the cloud, providing a software framework designed to manage, analyze and report on big data. 

Data is described as "big data" to indicate that is being collection is in ever escalating volumes, at increasingly high velocities, and for a widening variety of unstructured formats and variable semantic contexts. Big data collection does not provide value to an enterprise. For big data to provide value in the form of actionable intelligence or insight, it must be accessible, cleaned, analyzed, and then presented in a useful way, often in combination with data from various other sources. 

Apache Hadoop is a software framework that facilitates big data management and analysis. Apache Hadoop core provides reliable data storage with the Hadoop Distributed File System (HDFS), and a simple MapReduce programming model to process and analyze in parallel the data stored in this distributed system. HDFS uses data replication to address hardware failure issues that arise when deploying such highly distributed systems. 

To simplify the complexities of analyzing unstructured data from various sources, the MapReduce programming model provides a core abstraction that provides closure for map and reduce operations. The MapReduce programming model views all of its jobs as computations over key-value pair datasets. So both input and output files must contain such key-value pair datasets. Other Hadoop-related projects such as Pig and Hive are built on top of HDFS and the MapReduce framework, providing higher abstraction levels such as data flow control and querying, as well as additional functionality such as warehousing and mining, required to integrate big data analysis and end-to-end management.

Implementing Hadoop on Windows Azure as a service in the cloud makes the HDFS/MapReduce software framework and related projects available in a simpler, more scalable, and cost efficient environment. To simplify configuring and running Hadoop jobs and interacting with the deployed clusters, Microsoft provides JavaScript and Hive consoles. This simplified JavaScript approach enables IT professionals and a wider group of developers to deal with big data management and analysis by providing an accessible path into the Hadoop framework.

It addition to the available Hadoop-related ecosystem projects, it also provides Open Database Connectivity (ODBC) drivers to integrate Business Intelligence (BI) tools such as Excel, SQL Server Analysis Services, and Reporting Services, facilitating and simplifying end-to-end data analysis.
	
This topic describes the Hadoop ecosystem on Windows Azure, the main scenarios for Hadoop on Windows Azure cases, and provides a tour around the Hadoop on Windows Azure portal. It contains the following sections:

 * <a href="#BigData">Big Data: Volume, Velocity, Variety and Variability.</a> - The qualities of big data that render it best managed by NoSQL systems like Hadoop, rather than by conventional Relational Database Management System (RDBMS).

 * <a href="#Ecosystem">The Hadoop Ecosystem on Windows Azure </a> - Hadoop on Windows Azure provides Pig, Hive, Mahout, Pegasus, Sqoop, and Flume implementations, and supports other BI tools such as Excel, SQL Server Analysis Services and Reporting Services that are integrated with HDFS and the MapReduce framework.  

 * <a href="#Scenarios">Big Data Scenarios for Hadoop on Windows Azure</a> - The types of jobs appropriate for using Hadoop on Windows Azure.
 
 * <a href="#HadoopOnAzure">Getting Started with Microsoft Hadoop on Windows Azure</a> - Get Community Technical Preview (CTP) access and an introduction to the Apache™ Hadoop™-based Services for Windows Azure Portal.

 * <a href="#Tour">Tour of the Portal</a> - Deploying clusters, managing your account, running samples, and the interactive JavaScript console.

 * <a href="#Resources">Resources for Hadoop on Windows Azure</a> - Where to find resources with additional information.


<h2><a name="BigData"></a>Big data: volume, velocity, variety, and variability</h2>
You cannot manage or process big data by conventional RDBMS because big data volumes are too large, or because the data arrives at too high a velocity, or because the data structures variety and semantic variability do not fit relational database architectures. 

**Volume**	
The Hadoop big data solution is a response to two divergent trends. On the one hand, because the capacity of hard drives has continued to increase dramatically over the last 20 years, vast amounts of new data generated by web sites and by new device and instrumentation generations connected to the Internet, can be stored. In addition, there is automated tracking of everyone's online behavior. On the other hand, data access speeds on these larger capacity drives have not kept pace, so reading from and writing to very large disks is too slow. 

The solution for this network bandwidth bottleneck has two principal features. First, HDFS provides a type of distributed architecture that stores data on multiple disks with enabled parallel disk reading. Second, move any data processing computational requirements to the data-storing node, enabling access to the data as local as possible. The enhanced MapReduce performance depends on this design principle known as data locality. The idea saves bandwidth by moving programs to the data, rather than data to programs, resulting in the MapReduce programming model scaling linearly with the data set size. For an increase in the cluster size proportionately with the data processed volume, the job executes in more or less the same amount of time.

**Velocity**	
The rate at which data is becoming available to organizations has followed a trend very similar to the previously described escalating volume of data, and is being driven by increased ecommerce clickstream consumer behavior logging and by data associated social networking such as Facebook and Twitter. Smartphones and tablets device proliferation has dramatically increased the online data generation rate. Online gaming and scientific instrumentation are also generating streams of data at velocities with which traditional RDBMS are not able to cope. Insuring a competitive advantage in commercial and gaming activities requires quick responses as well as quick data analysis results. These high velocity data streams with tight feedback loops require a NoSQL approach like Hadoop's optimized for fast storage and retrieval.

**Variety**		
Most generated data is messy. Diverse data sources do not provide a static structure enabling traditional RDBMS timely management. Social networking data, for example, is typically text-based taking a wide variety of forms that may not remain fixed over time. Data from images and sensors feeds present similar challenges. This sort of unstructured data requires a flexible NoSQL system like Hadoop that enables providing sufficient structure to incoming data, storing it without requiring an exact schema. Cleaning up unstructured data is a significant processing part required to prepare unstructured data for use in an application. To make clean high-quality data more readily available, data marketplaces are competing and specializing in providing this service.

**Variability**		
Larger issues in the interpretation of big data can also arise. The term variability when applied to big data tends to refer specifically to the wide possible variance in meaning that can be encountered. Finding the most appropriate semantic context within which to interpret unstructured data can introduce significant complexities into the analysis. 


<h2><a name="Ecosystem"></a>The Hadoop ecosystem on Windows Azure</h2>

![TheHadoopEcosystem](../media/TheHadoopEcosystem.png "The Hadoop Ecosystem")

**Introduction** 	
Hadoop on Windows Azure offers a framework implementing Microsoft cloud-based solution for handling big data. This federated ecosystem manages and analyses large data amounts while exploiting parallel processing capabilities, other HDFS architecture optimizations, and the MapReduce programming model. Technologies such as Sqoop and Flume integrate HDFS with relational data stores and log files. Hive and Pig integrate data processing and warehousing capabilities. Pegasus provides graph-mining capabilities. Microsoft Big Data solution integrates with Microsoft BI tools, including SQL Server Analysis Services, Reporting Services, PowerPivot and Excel. Microsoft BI tools enable you to perform a straightforward BI on data stored and managed by the Hadoop on Windows Azure ecosystem. The Apache-compatible technologies and sister technologies are part of this ecosystem built to run on top of Hadoop clusters are itemized and briefly described in this section.

 **Pig**	
Pig is a high-level platform for processing big data on Hadoop clusters. Pig consists of a data flow language, called Pig Latin, supporting writing queries on large datasets and an execution environment running programs from a console. The Pig Latin programs consist of dataset transformation series converted under the covers, to a MapReduce program series. Pig Latin abstractions provide richer data structures than MapReduce, and perform for Hadoop what SQL performs for RDBMS systems. Pig Latin is fully extensible. User Defined Functions (UDFs), written in Java, Python, C#, or JavaScript, can be called to customize each processing path stage when composing the analysis. For more information, see [Welcome to Apache Pig!](http://pig.apache.org/)

 **Hive**	
Hive is a distributed data warehouse managing data stored in an HDFS. It is the Hadoop query engine. Hive is for analysts with strong SQL skills providing an SQL-like interface and a relational data model. Hive uses a language called HiveQL; a dialect of SQL. Hive, like Pig, is an abstraction on top of MapReduce and when run, Hive translates queries into a series of MapReduce jobs. Scenarios for Hive are closer in concept to those for RDBMS, and so are appropriate for use with more structured data. For unstructured data, Pig is better choice. Hadoop on Windows Azure includes an ODBC driver for Hive, which provides direct real-time querying from business intelligence tools such as Excel into Hadoop. For more information, see [Welcome to Apache Hive!](http://hive.apache.org/)

 **Mahout**		
Mahout is an open source machine-learning library facilitating building scalable matching learning libraries. Using the map/reduce paradigm, algorithms for clustering, classification, and batch-based collaborative filtering developed for Mahout are implemented on top of Apache Hadoop. For more information, see [What is Apache Mahout](http://mahout.apache.org/).

 **Pagasus**		
Pegasus is a peta-scale graph mining system running on Hadoop. Graph mining is data mining used to find the patterns, rules, and anomalies characterizing graphs. A graph in this context is a set of objects with links that exist between any two objects in the set. This structure type characterizes networks everywhere, including pages linked on the Web, computer and social networks (FaceBook, Twitter), and many biological and physical systems. Before Pegasus, the maximum graph size that could be mined incorporated millions of objects. By developing algorithms that run in parallel on top of a Hadoop cluster, Pegasus develops algorithms to mine graphs containing billions of objects. For more information, see the [Project Pegasus](http://www.cs.cmu.edu/~pegasus/) Web site.

 **Sqoop**		
Sqoop is tool that transfers bulk data between Hadoop and relational databases such a SQL, or other structured data stores, as efficiently as possible. Use Sqoop to import data from external structured data stores into the HDFS or related systems like Hive. Sqoop can also extract data from Hadoop and export the extracted data to external relational databases, enterprise data warehouses, or any other structured data store type. For more information, see the  [Apache Sqoop](http://sqoop.apache.org/) Web site.

**Flume**
Flume is a distributed, reliable, and available service for efficiently collecting, aggregating, and moving large log data amounts to HDFS. Flume's architecture is streaming data flow based. It is robust and fault tolerant with tunable and reliability mechanisms with many failover and recovery mechanisms. It has a simple extensible data model enabling online analytical applications. For more information, see the  [Flume](http://incubator.apache.org/flume/) incubation site.

 **Business intelligence tools**		
Familiar Business Intelligence (BI) tools such as Excel, PowerPivot, SQL Server Analysis Services and Reporting Services retrieves, analyzes, and reports data integrated with Hadoop on Windows Azure using ODBC drivers. The Hive ODBC driver and Hive Add-in for Excel are available for download on the _Hadoop on Windows Azure_ portal  [How To Connect Excel to Hadoop on Windows Azure via HiveODBC](http://social.technet.microsoft.com/wiki/contents/articles/6226.how-to-connect-excel-to-hadoop-on-azure-via-hiveodbc-en-us.aspx).	
 * For information Analysis Services, see [SQL Server 2012 Analysis Services](http://www.microsoft.com/sqlserver/en/us/solutions-technologies/business-intelligence/SQL-Server-2012-analysis-services.aspx).	
 * For information Reporting Services, see [SQL Server 2012 Reporting](http://www.microsoft.com/sqlserver/en/us/solutions-technologies/business-intelligence/SQL-Server-2012-reporting-services.aspx).	



<h2><a name="Scenarios"></a>Big data scenarios for Hadoop on Windows Azure</h2>
An exemplary scenario that provides a case for an Hadoop on Windows Azure application is an ad hoc analysis, in batch fashion, on an entire unstructured dataset stored on Windows Azure nodes, which do not require frequent updates.

These conditions apply to a wide variety of activities in business, science, and governance. These conditions include, for example, monitoring supply chains in retail, suspicious trading patterns in finance, demand patterns for public utilities and services, air and water quality from arrays of environmental sensors, or crime patterns in metropolitan areas.

Hadoop is most suitable for handling a large amount of logged or archived data that does not require frequent updating once it is written, and that is read often, typically to do a full analysis. This scenario is complementary to data more suitably handled by a RDBMS that require lesser amounts of data (Gigabytes instead of Petabytes), and that must be continually updated or queried for specific data points within the full dataset. RDBMS work best with structured data organized and stored according to a fixed schema. MapReduce works well with unstructured data with no predefined schema because it interprets data when being processed.

<h2><a name="HadoopOnAzure"></a>Getting started with Microsoft Hadoop on Windows Azure</h2>
**The Hadoop on Windows Azure CTP**		
The Hadoop on Windows Azure service is available by invitation only during this Community Technical Preview (CTP). The CTP purpose is for you to test Hadoop-based service on Windows Azure, become more familiar with it, and provide feedback. The process for gaining access is outlined below.

**The portal used by Apache Hadoop-based services for Windows Azure**		
The Microsoft implementation of Hadoop on Windows Azure uses a Portal to provision new Apache Hadoop clusters. Clusters provisioned on the portal are temporary and expire after several days. When there is less than six hours left on the clock, an expiration time extension is allowed. These clusters run jobs that process data either on the cluster or located elsewhere. For example, the data could reside in a Windows Azure account or be transferred to the cluster over FTP.
 
The advantage of using a temporary cluster is that there is no cost to maintain the hardware needed for the MapReduce parallel processing jobs. You use the cluster and then release it or allow it to expire. Apache Hadoop deployment solutions are also available for deploying Apache Hadoop to a Windows Azure account, or on-premise hardware that you manage. 

**Getting access to the CTP and deploying an Hadoop cluster**	
The steps for getting access to the Hadoop on Windows Azure, logging into the site and deploying your first Hadoop cluster on Windows Azure are as follows.
		
 1. Provide information about yourself, business domain, and technical scenario by completing the [Apache Hadoop for Windows Azure & Windows Server](https://connect.microsoft.com/continue.aspx?pageType=2&regType=1&cru=%2fSQLServer%2fSurvey%2fSurvey.aspx%3fSurveyID%3d13697&cu=) Connect profile. You need a LiveID (for example, Hotmail.com, Live.com) to complete and submit the Connect profile. This may require some preliminary steps.				
 2. Once you receive an invite code, go to the [HadoopOnAzure.com](https://www.hadooponazure.com/HadoopOnAzure.com) site and click **Sign In**.		
 3.	If it is your first time, you are asked to allow _HadoopOnAzure.com_ access to your LiveID profile information. Click **Yes**. The _Got a code_ dialog box opens.

 4. In the _Got a code_ dialog box, enter invite code, and then click **Enroll**.		
 5. For a new account, your first task is to create a Hadoop on Windows Azure cluster. Your options are as follows: 
![RequestNewCluster](../media/RequestNewCluster.PNG) 
Your options are:	
**DNS Name**: Choose a name for your cluster. Here "samples8" is used.			
**Cluster Size**: Select what size of cluster to test against. Currently, the **Small** 3 node cluster must be used.	
**Cluster Login**: Provide a **Username** for the cluster and **Password** for logging into it. Here "someUserName" the default value, is used.
 6. Click **Request cluster** (right side bar, under the green bar)	
 7. At this point, the Hadoop on Windows Azure service begins creating the new cluster, which takes up to tens of minutes, depending on the number of nodes and the number of clusters. 		


<h2><a name="Tour"></a>Tour of the portal</h2>
 
Once logged in with a deployed cluster, your account page opens.

![HadoopOnAzureAccountPage](../media/HadoopOnAzureAccountPage.PNG "Hadoop on Windows Azure Account Page")
	
*The Hadoop on Windows Azure Portal*

There are three sections on the portal grouping the icons linked to Hadoop on Windows Azure management features: 

 * **Your Tasks**: This section enables you to create new jobs and keep track of jobs you have previously created or run.
 * **Your Cluster**: This section provides several methods to interact with and manage your cluster, for example, the **Interactive Console** for JavaScript and Hive, **Remote Desktop** to access the cluster directly, the ability to **Open Ports** for ODCB FTPS connections, and **Manage Cluster** storage, data markets, disaster recovery, and connections to your Amazon S3 account.
 * **Manage your Account**: This section tracks **Job History** on your account, gives access to the **Samples** that come ready to run with Hadoop on Windows Azure, and provides **Downloads** of client utilities for Hadoop on Windows Azure, such as the Hive ODBC driver and Hive Add-in for Excel. (The **Billing History** can be ignored during the developer preview.)

To explore Portal functionality, click any icon. For use of the **New Jobs** and **Interactive Console** functionality, see the _Running Jobs with Hadoop on Windows Azure_ topic. For walkthroughs on running the **Samples**, see the _Samples_ topics. You can use the Hadoop file system commands from the command window on the head node, which is available in the **Remote Desktop**.

<h2><a name="Resources"></a>Resources  for Hadoop on Windows Azure</h2>
**Microsoft: Hadoop on Windows Azure**	

* [Welcome to Hadoop on Windows Azure](https://www.hadooponazure.com/) - the welcome page for the Developer Preview for the Apache Hadoop-based Services for Windows Azure.	
* [Apache Hadoop-based Services for Windows Azure How To Guide](http://social.technet.microsoft.com/wiki/contents/articles/6206.hadoop-based-services-on-windows-azure-how-to-guide.aspx) - TechNet wiki with links to Hadoop on Windows Azure documentation.	
* [Big Data and Windows Azure](http://www.windowsazure.com/en-us/home/scenarios/big-data/) - Big Data scenarios that explore what you can build with Windows Azure.	

**Microsoft: Windows and SQL Database**	

* [Windows Azure home page](https://www.windowsazure.com/en-us/) - scenarios, free trial sign up, development tools and documentation that you need get started building applications.		
* [MSDN SQL Database](http://msdn.microsoft.com/en-us/library/windowsazure/ee336279.aspx)	- MSDN documentation for SQL Database	
* [Management Portal for SQL Database](http://msdn.microsoft.com/en-us/library/windowsazure/gg442309.aspx) - a lightweight and easy-to-use database management tool for managing SQL Database in the cloud.
* [Adventure Works for SQL Database](http://msftdbprodsamples.codeplex.com/releases/view/37304) - Download page for SQL Databse sample database.	

**Microsoft: Business Intelligence**		

* [Microsoft BI PowerPivot](http://www.microsoft.com/en-us/bi/PowerPivot.aspx) - a powerful data mashup and data exploration tool. 				
* [SQL Server 2012 Analysis Services](http://www.microsoft.com/sqlserver/en/us/solutions-technologies/business-intelligence/SQL-Server-2012-analysis-services.aspx) - build comprehensive, enterprise-scale analytic solutions that deliver actionable insights.	
* [SQL Server 2012 Reporting](http://www.microsoft.com/sqlserver/en/us/solutions-technologies/business-intelligence/SQL-Server-2012-reporting-services.aspx) - a comprehensive, highly scalable solution that enables real-time decision making across the enterprise. 
	
**Apache Hadoop**:			

* [Apache Hadoop](http://hadoop.apache.org/) - software library providing a framework that allows for the distributed processing of large data sets across clusters of computers.	
* [HDFS](http://hadoop.apache.org/hdfs/) - Hadoop Distributed File System (HDFS) is the primary storage system used by Hadoop applications.		
* [Map Reduce](http://hadoop.apache.org/mapreduce/) - a programming model and software framework for writing applications that rapidly process vast amounts of data in parallel on large clusters of compute nodes.		
