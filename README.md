# jRedisConnect

Redis Streams were just released and so it might be useful to write some connectors in order ingest some real-time data from other sources. 

> This project is currently in the planning phase.

## Requirements

|Id|Name|Descr|
|---|---|---|
|0|Connector Service|General requirements for a Connector service|
|0.1|Standalone|It should be possible to run jRedisConnect in a service/daemon mode|
|0.2|Tenancy|A Redis connect service should be able to run multiple connectors the same time|
|0.3|Scheduled termination|For testing purposes it should be possible to run the service for just a few seconds and then terminate|
|1|Configuration|
|1.1|Declarative|It needs to possible to declare how the connector should behave|
|1.2|Well defined|A well defined config format is needed|
|2|Mapping||
|2.1|Filtering|It needs to be possible to filter ingested elements out|
|2.2|Coversions|It needs to be possible to convert ingested elements into the right format in order to be stored in Redis|
|3|Scalability||
|3.1|Service level scalability|The service needs to be scalable, so multiple such services need to act with awareness of each other in a cluster|
|3.2|Partioning|It needs to be possible to spread the data across multiple Redis streams|
|4|High availability||
|4.1|Service level availability|It needs to be possible to loose a connector service node|
|4.2|Data availability|The service needs to be able to deal with temp. failures on the Redis side|

## Design

The following components can be derived from the above mentioned requirments

|Service||
|---|---|
|...|...|

--> 1 ..n -->

|Connector||
|---|---|
|...|...|

|Execution Scheduler||
|---|---|
|...|...|

|Configuration||
|---|---|
|...|...|

|Filter||
|---|---|
|...|...|

|Converter||
|---|---|
|...|...|

|Cluster||
|---|---|
|...|...|

|Partition||
|---|---|
|...|...|

|Failure Handler||
|---|---|
|...|...|
