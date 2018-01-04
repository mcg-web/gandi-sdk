# Gandi SDK

Gandi API PHP SDK.

[![Latest Stable Version](https://poser.pugx.org/nexylan/gandi-sdk/v/stable)](https://packagist.org/packages/nexylan/gandi-sdk)
[![Latest Unstable Version](https://poser.pugx.org/nexylan/gandi-sdk/v/unstable)](https://packagist.org/packages/nexylan/gandi-sdk)
[![License](https://poser.pugx.org/nexylan/gandi-sdk/license)](https://packagist.org/packages/nexylan/gandi-sdk)

[![Total Downloads](https://poser.pugx.org/nexylan/gandi-sdk/downloads)](https://packagist.org/packages/nexylan/gandi-sdk)
[![Monthly Downloads](https://poser.pugx.org/nexylan/gandi-sdk/d/monthly)](https://packagist.org/packages/nexylan/gandi-sdk)
[![Daily Downloads](https://poser.pugx.org/nexylan/gandi-sdk/d/daily)](https://packagist.org/packages/nexylan/gandi-sdk)

## Documentation

All the installation and usage instructions are located in this README.
Check it for a specific versions:

* [__0.x__](https://github.com/nexylan/gandi-sdk/tree/master)

## Installation

First of all, you need to require this library through Composer:

``` bash
composer require nexylan/gandi-sdk
```

With Symfony:

Enable the bundle on the `AppKernel` class:

```php
// app/AppKernel.php

public function registerBundles()
{
    $bundles = array(
        // ...
        new Nexy\Gandi\Bridge\Symfony\Bundle\NexyGandiBundle(),
    );

    // ...

    return $bundles
}
```

## Configuration

Configure the bundle to your needs:

```yaml
# parameters.yml
parameters:
    # Change to https://rpc.gandi.net/xmlrpc/ in prod
    gandi_api_url: https://rpc.ote.gandi.net/xmlrpc/
```


```yaml
# config.yml
nexy_gandi:
    api_url: %gandi_api_url%
    api_key: 'yourApiKey'
```

## Usage

Use the predefined methods and/or use Gandi methods directly

```php
$gandi = new Gandi('api_url', 'api_key');

$result = $gandi->setup()->domain->info('mydomain.net');

// Results
// [
//     status => [
//         0 => clientTransferProhibited
//     ]
//     zone_id => 42
//     fqdn => mydomain.net
//     // ...
// ]
```
