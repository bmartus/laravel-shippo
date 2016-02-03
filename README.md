Shippo for Laravel 5
==============

Integrates the Shippo PHP library with Laravel 5 via a ServiceProvider.

### Installation

Include laravel-shippo as a dependency in composer.json:

~~~
"bmartus/laravel-shippo": "dev-master"
~~~

Run `composer install` to download the dependency.

Add the ServiceProvider to your provider array within `app/config/app.php`:

~~~
'providers' => [
    ...
    Bmartus\LaravelShippo\LaravelShippoServiceProvider::class,
]
~~~

### Configuration

Add the following to your `.env` file:
~~~
SHIPPO_API_KEY=key_from_shippo
~~~

### Usage

You may use the [Shippo PHP Library](https://github.com/goshippo/shippo-php-client) as normal within your application. The Shippo API will automatically be configured with your API Key, so you do not need to set it yourself.

### Example

A quick example in `routes.php`: 
~~~
<?php

Route::get('/address', function() {

    return \Shippo_Address::create([
        'object_purpose' => 'QUOTE',
        'name' => 'John Smith',
        'company' => 'Initech',
        'street1' => 'Greene Rd.',
        'street_no' => '6512',
        'street2' => '',
        'city' => 'Woodridge',
        'state' => 'IL',
        'zip' => '60517',
        'country' => 'US',
        'phone' => '123 353 2345',
        'email' => 'jmercouris@iit.com',
        'metadata' => 'Customer ID 234;234'
    ]);

});

~~~
