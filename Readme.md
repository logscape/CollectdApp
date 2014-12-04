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
    Host "10.28.1.159"
    Port "9991"
    Prefix "LOGSCAPETOKEN:-6e6e377b:149f1428863:-7fc6 LOGSCAPETAG:collectd type:collectd "
    Postfix ""
    StoreRates false
    AlwaysAppendDS false
    EscapeCharacter ""
  </Carbon>
</Plugin>
```

Replace Host with the location of your logscape installation. The LOGSCAPETOKEN and LOGSCAPETAG are used when pointing collectd to Logcape Cloud. Replace LOGSCAPETOKEN with your unique otoken. 


The LoadPlugin directive is required to enable the plugin. Restart collectd to start importing metrics in Logscape

 The CollectdApp has 4 main categories.

 * System Overview  
 * Sensors - CPU Temperatures,Fan speed and so on  etc 
 * CPU - Cpu Utilization, Context Switching 
 * Memory - Memory Utilization, Caches, Virtual Memory stats such as page faults, paging in and out 
 * Network - Network Packets, Errors 
 * Disk - Disk Utilization, Operations and disk time ( what is reported by Collectd can not be trusted ) 

The collectd data type based on the Collectd schema for reporting metric data. See the [collectd naming schema](https://collectd.org/wiki/index.php/Naming_schema)

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

