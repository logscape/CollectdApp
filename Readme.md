# 

 The CollectdApp has 4 main categories.

 * System Overview  
 * Sensors - CPU Temperatures,Fan speed and so on  etc 
 * CPU - Cpu Utilization, Context Switching 
 * Memory - Memory Utilization, Caches, Virtual Memory stats such as page faults, paging in and out 
 * Network - Network Packets, Errors 
 * Disk - Disk Utilization, Operations and disk time ( what is reported by Collectd can not be trusted ) 
 * Custom - Tutorial on how to add a plugin 

There are other searches and dashboards available but they can not be reached from the Collectd Home Workspace. These are 

 * Processes - Process State, running, sleeping etc
 * Protocols - Network protocol state. Ports open and so on 
 *  

# Configuring Collectd Server

 To configure the app you will need to 
 * Set up a central collectd server  - See the collectd Network Plugin. Traffic can now be signed and/or encrypted. 
 * Configure the collectd output direactory and make sure the name has '_SERVER' appended to it.e.g  $MYOUTPUTDIR_SERVER_  -  
 * Configure the rate of the metrics - you won''t need everything and there is a lot of data that gets produced. 
 * Add the CSV plugin 

	<Plugin csv>
        	DataDir "/var/lib/collectd/remote_SERVER_"
	#       StoreRates false
	</Plugin>
 This will store all your collectd metrics in a csv format on the file system. 

 To configure a the collectd server to accept metrics from collectd clients add this to your configure. This config will confirm that the different machines are talking to each other.  R
 Read the collectd documentation on securing the network plugin. 

	<Plugin network>
		Listen "10.28.1.163" "9999"
	        ReportStats false
	</Plugin>


# Configure you collectd Client

 This creates a create an unsecure client connection. See the collectd documentation for hardenining collectd clients.

	<Plugin network>
        	Server "10.28.1.163" "9999"
	        ReportStats false
	</Plugin>


# Download the CollectdApp 

 Download the Collectd App and then deploy it. 



# Configure your Collectd Data Source  

 * Add a data source called collectd 
 * Point the data source to $MYOUTPUT_SERVER_
 * Save   


#  Exploring the App

