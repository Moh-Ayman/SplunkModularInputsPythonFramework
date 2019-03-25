# Splunk Command Modular Input v1.2
by www.baboonbones.com
May 2018
----

## Overview

This is a Splunk Modular Input for executing commands and indexing the output.
It is quite simply just a wrapper around whatever system commands/programs that you want to periodically execute and capture the output from ie: (top, ps, iostat, tshark, tcpdump etc...). It will work on all supported Splunk platforms.

## Dependencies

* Splunk 5.0+
* Supported on Windows, Linux, MacOS, Solaris, FreeBSD, HP-UX, AIX

## Setup

* Untar the release to your $SPLUNK_HOME/etc/apps directory
* Restart Splunk

## Activation Key

You require an activation key to use this App. Visit http://www.baboonbones.com/#activation to obtain a non-expiring key

## Custom Output Handlers

You can provide your own custom Output Handler. This is a Python class that you should add to the 
command_ta/bin/outputhandlers.py module.

You can then declare this class name and any parameters in the Command Input setup page.

## Streaming vs Non Streaming Command Output

Some commands will keep STD OUT open and stream results.For these scenarios ensure you check the "streaming output" option on the setup page.

## Environment variables
Environnment variables in the format $VARIABLE$ can be included in the command name and command arguments and they will be dynamically substituted ie: $SPLUNK_HOME$

## Logging

Any modular input errors will get written to $SPLUNK_HOME/var/log/splunk/splunkd.log


## Troubleshooting

* You are using Splunk 5+
* You have permissions to execute the command
* The command is on the system PATH if you're just specifying the command name
* The path to the command is correct if you're specifying the full path to the command
* The command arguments are correct
* The command is installed
* You have configured timestamping for the sourcetype correctly
* Look for any errors in $SPLUNK_HOME/var/log/splunk/splunkd.log
