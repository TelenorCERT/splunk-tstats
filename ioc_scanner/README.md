# IOC SCANNER

Do you have any logs with this IOC (IP or HASH)?

The IOC scanner is not a finished product you can just install, but a few methods to solve a common problem. Your sources are telling you that this IOC is bad.

How to tell if the IOC is in any of your logs without searching in every index for the IOC.

- Creating a lookuptable of all index-sourcetype-field combinations that contain an IP or HASH.
- Create a Dashboard that only search those combinations for the IOC.

With a very large Splunk platform, this is a time saver!

