# CollectdApp-1.0 

The Collectd App provide dashboard, data type mappings for collectd input plugins. Collectd is a monitoring daemon run on unix systems gathering system health metrics.

## Downloads 

 * [CollectdApp]
 * 


## Configuration

Logscape imports collectd data using the graphite write plugin. Most linux distributions will have this plugin installed. To configure update the Prefix and Postfix parameters of the graphite plugin as shown in the example below.


```xml
LoadPlugin write_graphite
<Plugin write_graphite>
  <Carbon>
    #Host "10.28.0.150"
    Host "10.28.1.159"
    #Port "8991"
    Port "9991"
    Prefix "LOGSCAPETOKEN:-6e6e377b:149f1428863:-7fc6 LOGSCAPETAG:collectd type:collectd "
    Postfix ""
    StoreRates false
    AlwaysAppendDS false
    EscapeCharacter ""
  </Carbon>
</Plugin>
```


The LoadPlugin directive is required to enable the plugin. Restart collectd to start importing metrics in Logscape


##


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

## Sample Screenshots


### Sensors

![](doc/images/collectd_sensors.png) 

### System Load 

![](doc/images/collectd_load.png) 

## Network 
![](doc/images/collectd_network.png)

## Memory 

![](doc/images/collectd_memory.png)

### 

