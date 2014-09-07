This package is still **UNDER DEVELOPMENT** but feel free to try it as you wish.

## Larapush - WebSocket and Push server

#### a [Ratchet](http://socketo.me) and [ZMQ](http://zeromq.org) implementation for Laravel 4.

#### ZMQ is required
--------------------

Make sure to have **ZMQ installed** on your system before to try it. [Install guide](http://zeromq.org/bindings:php)



#### How to install this package
--------------------------------

```
// composer.json

{
    "require": {
        "redbaron76/larapush": "dev-master"
    }
}
```

```php
// app/config/app.php

'providers' => array(

		...

		'Redbaron76\Larapush\LarapushServiceProvider',
	),
```

Then run `composer update` to install the new package.



#### How to use
---------------

##### 1) Start the Larapush server

   From the console just type `php artisan larapush:serve` to rise the WebSocket/Ratchet server up.

##### 2) Use the Larapush facade in your routes to trigger events server-side

```php
// app/routes.php

Route::any('profile/{nickname}', ['as' => 'profile', function($nickname)
{
	Larapush::send(['message' => 'I watch you, '.$nickname.'!'], ['profileChannel'], 'profile.visit');

	return View::make('some.view');
}]);
```

##### 3) Subscribe your client to **channels** and listen for **events** in the client-side



#### [Larapush.js](https://github.com/redbaron76/Larapush.js) - Pub/Sub js lib for Larapush
-------------------------------------------------------------------------------------------

In order to make your dev life easier with Larapush, please give [Larapush.js](https://github.com/redbaron76/Larapush.js) a try.

###### Follow my Twitter account [@FFumis](http://twitter.com/FFumis) for any update. 