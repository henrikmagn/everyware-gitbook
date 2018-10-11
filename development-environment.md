# Development environment

## Requirements

Following apps/programs are required to work with a Everyware-site

* Docker
* Git
* Composer 
* Terminal-client

### Project specific requirements

Some projects have other requirement upon the standard. These should be specified in the project **README.md** file.

### Log files

Log files are automatically created in the project folder in the subfolder "log".

* access.log \(nginx access log\)
* error.log \(nginx error log\)
* php-fpm-error.log \(php-fpm error log\)

Follow logs with

```bash
tail -f log/error.log
```

### Commands 

The Makefile has some useful funtions that is good to know when working with the development environment. All commands can be run without the Makefile but it simplifies the usage.

```bash
make start            # Start the environment.
make stop             # Stop the environment.
make restart          # Restart the environment.
make pull             # Fetch latest version of Docker images.
make restart-full     # Stop, remove, pull and start.
make luarocks         # Install luarock dependencies.
make remove           # Removes all containers EXCEPT mysql.
make remove-mysql     # Removes mysql container, all mysql data will be deleted. 
make nginx-restart    # Restart nginx, useful when configuring nginx.
make mysql-dump       # Dump the local database to a sql-file.
make redis-flush      # Flush redis, clears both front and object cache.
```

