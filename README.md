# smon

Simple MONitoring tool

## Features

`smon` includes these probes:
   - **TCP** for testing TCP connections;
   - **HTTP** for testing HTTP responses, status codes and response lengths;
   - **PING** for testing ICMP replies;
   - **CERT** for validating X.509 certificates and days until their expiration.
  
 The following reporting methods are available:
 
   - setting an **exit code**;
   - logging to a **standard output**;
   - mailing via **sendmail**;
   - writing to a **syslog**;
   - making a **HTTP request** (chat bots and other external tools).

## Installation

```
git clone https://github.com/ondras/smon.git
```

## Configuration

  1. Create the `conf/` subdirectory
  1. Put all your configuration inside:
    1. Configuration files are CommonJS modules (i.e. JavaScript files)
    1. All files in `conf/` are used; you can either create one-file-per-configuration-element or use one file for all configuration
    1. The `conf-example/` directory shows several examples for probes and reporters

The configuration API has these methods:

```js
require("..").addProbe({ /* probe configuration */ });

require("..").addReporter({ /* reporter configuration */ });

require("..").configure({ /* global options */ });
```


## Running

```
node .
```

If you have a recent node (6.2+) and your symlinked conffiles are broken, try:

```
node --preserve-symlinks .
```
