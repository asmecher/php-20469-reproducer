# php-20469-reproducer

Reproduce [bug #20469 (maybe)](https://github.com/php/php-src/issues/20469) in PHP.

Steps:
1. Run `composer install` (to build the autoload configuration)
2. Run the PHP built-in web server: `php -S 127.0.0.1:8080`
3. Run `wget http://localhost:8080/test1.php` to trigger `test1.php`
4. Run `wget http://localhost:8080/test2.php` to trigger `test2.php`
5. The PHP built-in webserver will terminate with a segfault.

While I wasn't able to reproduce this outside the built-in webserver, I doubt it's limited to that environment.

Tested with PHP versions 8.4.16, 8.3.29, 8.2.30, and 8.1.34 (on an Ubuntu system). All were affected.
