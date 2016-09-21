# Speeding up incident response using Splunk.

The path to *Warp Speed* incident response.

It might also be basic Splunk methods we would like to share.

# Event Flow Tracker

Do you really know where your log events are?

This APP includes a Dashboard that uses tstats to visualize incoming log events
to your indexes. This is more like a practical guide to tstats and the use of
already available metadata instead of fetching all events from disk.

If your data is within the reach of tstats, you should consider using that
instead of normal searches for your dashboards.

Would you waste The Analysts time?


# IOC scanner

IOC, Indicator of compromise.

While our friend, The Analyst, have a great amount of knowledge, it is
impossible to follow everything the rest of the enterprise do.

An IOC scanner, will speed the work looking for known bad IPaddresses and
Hashes in both known and unknown logs in Splunk.

This is more like a story to get to the great results, and it might just need a
SPL ninja to get right from the search to the result. The limitations are everywhere.




