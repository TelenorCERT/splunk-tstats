# Event Flow Tracker

Do you really know where your log events are?

We index a lot of data that we need if there should be a security incident. If the data is not there when we need it, it would kind of make us look bad.
But more importantly, it would make incident response a lot harder than it needs to be.

Monitoring that the streams of events you expect to have in Splunk, actually are there, is very very important.

This APP includes a Dashboard that uses tstats to visualize incoming log events to your indexes.
We have only included very basic seaches and it will be more like a practical guide to tstats.

How to use already available metadata instead of fetching all events from disk.

## Introduction to tstats

The tstats command is used to perform statistical queries on indexed fields in
Splunk. These can be normal indexed fields like host, source, sourcetype,
punct, _time and _indextime, but also datamodels.

### Basic usage
If you are running Splunk on your laptop and wants to count some events in an index, you can use the *| stats count* command.

In this example there are 100 million events in *index=main* and the result was ready in 42 seconds.

```
index=main |stats count
```


With tstats, you collect the data from the tsidx-file in the bucket instead of retrieving all events from disk.  The result was ready in less than a second!

```
|tstats count WHERE index=main
```

### tstats and time
These two will result in 168 events (There are 168 hours in 7 days). In our example, we scanned 3.011.776.384 events in 4.183 seconds.

Create a table with results
```
|tstats count WHERE index=main earliest=-7d@d latest=@d BY _time span=1h
```

Use prestats=true when you need to pipe the result to a command that requires the prstats format. chart and timechart are common examples.
```
|tstats prestats=true count WHERE index=main earliest=-7d@d latest=@d BY _time span=1h |timechart span=1h count

```
