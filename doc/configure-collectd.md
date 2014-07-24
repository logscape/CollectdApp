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

