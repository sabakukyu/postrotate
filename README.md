# **postrotate**

The *postrotate* script is designed to rotate logs in combination with the *logrotate* utility. The *logrotate* utility archive old logs adding a suffix (e.g. a date) and once completed, run *postrotate* script to generate new logs without suffix and swap file descriptors (open file descriptors to the generated logs and close file descriptors of the rotated logs).

Log rotation will only work if the suffix added by *logrotate* utility is the same as that passed to *postrotate* script and if rotated logs are not compressed (compression will break file descriptors).

## Requirements

The *postrotate* script is programmed for *bash* shell and requires some utilities/commands to work properly:

  * *logrotate* (discussed above)
  * *gdb* (GNU Debugger)

All other required commands (such as: *find*, *fuser*, *grep*, *sed*, *...*) are very common and are not listed.

## Usage

```sh
$ ./postrotate --help
Usage: ./postrotate [-h] [-v] -d directory [-s suffix]

  -d, --dir
    Specifies the logs directory location (no trailing slash). The directory
    location must be valid and writable.

  -h, --help
    Shows this help message.

  -s, --suffix
    Specifies the suffix of the rotated logs. Default value is '_%Y-%m-%d'.

  -v, --verbose
    Enable verbose logging of what postrotate is doing.

Example: ./postrotate -d /service/tomcat/logs -s _%Y-%m-%d
```

## To-Do

  * Add code comments
  * Error handling

## 

Joaquín José García Cañas (https://github.com/sabakukyu)
