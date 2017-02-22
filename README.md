# GraylogExtractor


## Sophos Web Appliance

This one is a little hacky, and I'm sure there is a better way to do it. You need to add the Input as RAW / Plaintext UDP.

This is because it seems Sophos is sending the Timestamp in the SysLog in another TimeZone as Configured. I think it always uses +00:00. And I haven't found a way to convert it without using other extractors.
Using RAW / Plaintext Graylog creates the Timestamp on its own.

### How to use

You have to create a new RAW / Plaintext UDP Input and add / import the extractor to it.

On the Web Appliance you have to "Enable Syslog transfer of web traffic". You find this under 

Configuration / System / Alerts & Monitoring / SysLog

Here you just add the needed data and select UDP.

To better understand the Values of all the fields you can use [this, starting on Page 224](http://wsa.sophos.com/ug/pdf/swa_ug.pdf).

