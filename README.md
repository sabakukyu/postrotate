# Postrotate

The *postrotate* script is designed to rotate logs in combination with the *logrotate* utility. The *logrotate* utility archive old logs adding a date extension (format: *_%Y-%m-%d*) without compression. After it completes logs rotation, run *postrotate* script to generate new logs without extension and swap file descriptors (open file descriptors to the generated logs and close file descriptors of the rotated logs).

### Requirements

The *postrotate* script is programmed for *bash* shell and requires some utilities/commands to work properly:

  * *logrotate* (discussed above)
  * *gdb* (GNU Debugger)

All other required commands (such as: *find*, *fuser*, *grep*, *sed*, *...*) are very common and are not listed.

### Usage

```sh
$ ./postrotate --help
Usage: ./postrotate [-h] [-v] -d directory

  -d, --dir
    Specifies logs directory location (no trailing slash). The directory location must be valid
    and writable.

  -h, --help
    Shows this help message.

  -v, --verbose
    Enable verbose logging of what postrotate is doing.

Example: ./postrotate -d /service/tomcat/logs
```

### Version

1.0.0

### To-Do

  * Add Code Comments

### 

Joaquín José García Cañas
