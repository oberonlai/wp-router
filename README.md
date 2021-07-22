# WP Router v1.0

Easily add custom URL endpoints in WordPress. Map a url to a function. Modifed from [wordpress-dispatcher](https://github.com/tim-field/wordpress-dispatcher) 

## Requirements

* PHP >=7.2
* [Composer](https://getcomposer.org/)
* [WordPress](https://wordpress.org) >=5.4

## Installation

#### Install with composer

Run the following in your terminal to install with [Composer](https://getcomposer.org/).

```
$ composer require oberonlai/wp-router
```

WP Router [PSR-4](https://www.php-fig.org/psr/psr-4/) autoloading and can be used with the Composer's autoloader. Below is a basic example of getting started, though your setup may be different depending on how you are using Composer.

```php
require __DIR__ . '/vendor/autoload.php';

use ODS\Router;

Router::routes( array() );

```

See Composer's [basic usage](https://getcomposer.org/doc/01-basic-usage.md#autoloading) guide for details on working with Composer and autoloading.

## Example

```php
use ODS\Router;

Router::routes( 
	array (
		'testing-a-url' => function(){
		    echo 'Hello Ted';
		},

		'hello-([a-z]+)' => function($request, $name){
		    echo "Hello $name";
		}
	)
);
```

/testing-a-url & /hello-dougle will now be accessable in your WordPress site.