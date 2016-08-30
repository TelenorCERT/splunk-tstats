# splunk-tstats
Speeding up incident response using Splunk.
To Achieve Warp Speed.


# Event Flow Tracker

Do you really know where your log events are?
This Dashboard is using tsats and splunk to visualize incoming log events to your indexes. 

Using tstats to do the heavy lifting, this Splunk dashbard should be loading at
warp speed. Even if you have a billion events to parse in your index. 

## Introduction to tstats

The tstats command is used to perform statistical queries on indexed fields in
Splunk. These can be normal indexed fields like host, source, sourcetype,
punct, _time and _indextime, but also datamodels.

### Examples
If you are running Splunk on your laptop and wants to count some events in an index, you can use the *| stats count* command. 

In this example there are 100 million events in *index=main* and the result was ready in 42 seconds.

```
index=main |stats count
```


With tstats, you collect the data from the tsidx-file in the bucket instead of retrieving all events from disk. 

```
|tstats count WHERE index=main
```

The result was ready in less than a second!
 

