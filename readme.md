Apache+PHP build pack
========================

This is a build pack bundling PHP and Apache for Heroku apps. It tests for the presence of an `index.html` or `index.php` file and then serves out of root with Apache.

Use
---

For new apps:
```bash
$ heroku create --stack cedar --buildpack https://github.com/firstandthird/heroku-buildpack-ruby.git
```

For existing apps:
```bash
$ heroku config:add BUILDPACK_URL=https://github.com/firstandthird/heroku-buildpack-apache.git
```

For dokku:
In your root directory, create a file called `.env` with the following contents:
```bash
BUILDPACK_URL=https://github.com/firstandthird/heroku-buildpack-apache.git
```

Basic Authentication
--------------------

in .htaccess add:
```
AuthUserFile /app/.htpasswd
AuthType Basic
AuthName "Restricted Access"
Require valid-user
```

[generate](http://www.htaccesstools.com/htpasswd-generator/) and add an .htpasswd to root


Configuration
-------------

The config files are bundled with the build pack itself:

* conf/httpd.conf
* conf/php.ini


Meta
----

Big thanks to the guys behind the [php buildpack](https://github.com/heroku/heroku-buildpack-php)

Released under the [MIT License](http://opensource.org/licenses/mit-license.php)
