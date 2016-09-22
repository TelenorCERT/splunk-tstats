# IOC SCANNER

The IOC scanner is not a finished product you can just install, but a few methods to solve a common problem.
IOC stands for Indicator Of Compromise, and are typically shared between security professionals.

- Do you have any logs with this IOC (IP or HASH)?
- What do you do when your sources are telling you that this IOC is bad?

How to tell if the IOC is in any of your logs without searching in every index for the IOC.

- Creating a lookuptable of all index-sourcetype-field combinations that contain an IP or HASH.
  - discover_ipv4_fields
  - discover_md5_fields
  - discover_sha1_fields
  - ....

- Create a Dashboard that only search those combinations for the IOC.
  - ioc_scan.xml

With a very large Splunk platform, this is a time saver!

The idea was developed by Alex Teixeira, Splunk Professional Services.
