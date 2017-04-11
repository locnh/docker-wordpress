## Supported tags and respective `Dockerfile` links
* [`latest` (*2.x/Dockerfile*)](https://github.com/locnh/docker-wordpress/blob/master/Dockerfile)

## What is this ?
Docker container built with CentOS 7, NGINX (or HTTPD) and PHP 7 with compatible version and modules for Wordpress

These are the Docker Hub autobuild images located [here](https://hub.docker.com/r/locnh/docker-wordpress/).

![Wordpress Logo](https://s.w.org/about/images/logos/wordpress-logo-stacked-rgb.png)

## How to start
### The Simplest way, NginX - PHP-FPM by default
1. Pull the latest image

  ```
  $ docker pull locnh/docker-wordpress
  ```

2. Create container

  ```
  $ docker run --name wordpress -v /path/to/wordpress:/var/www/html -p 80:80 -d locnh/docker-wordpress
  ```

That's it !

## More Options

#### Using Apache (httpd) instead of NginX
- Just add the environment variable with `-e WEB_SRV=apache` or `-e WEB_SRV=httpd`
- Example:

  ```
  $ docker run --name wordpress -e WEB_SRV=httpd -v /path/to/wordpress:/var/www/html -p 80:80 -d locnh/docker-wordpress
  ```


#### Set the `uid` (and/or `gid`) of `apache` inside container
- To change the apache `uid`, use `-e UID=<your uid>` (you can use this).
- To change the apache `gid`, use `-e GID=<your gid>` (use at your own risk).
- Example:

  ```
  $ docker run --name wordpress -e UID=501 -v /path/to/wordpress:/var/www/html -p 80:80 -d locnh/docker-wordpress
  ```


#### Mountable Volumes
Beside Webroot `/var/www/html`, you can use option `-v` to mount more volumes to the container such as services logs:
- NginX logs:   `/var/log/nginx`
- Apache logs:  `/var/log/httpd`
- PHP-FPM logs: `/var/www/php-fpm`

## Contribute
1. Fork me
2. Make changes
3. Create pull request
4. Grab a cup of coffee
