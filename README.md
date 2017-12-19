# Marketplace.tf PHP bindings ![Travis](https://api.travis-ci.org/fiskie/php-marketplace-tf-api.svg?branch=master)

Provides bindings for the public Marketplace.tf web APIs. Software design is based on da-mitchell's Steam API bindings.

## Composer

```
composer require fisk/marketplace
```

## Usage

```
<?php
$config = new Configuration([
    Configuration::API_KEY => ''
]);

$client = new Marketplace($config);
$client->addRunner(new GuzzleRunner(new Client(), new GuzzleUrlBuilder()));
$client->addRunner(new DecodeJsonStringRunner());

$result = $client->run(new GetDashboardItems());

print_r($result);
?>
```
