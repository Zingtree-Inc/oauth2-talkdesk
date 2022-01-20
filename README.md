# Talkdesk Provider for OAuth 2.0 Client

[![Latest Version](https://img.shields.io/github/release/zingtree-inc/oauth2-talkdesk.svg?style=flat-square)](https://github.com/zingtree-inc/oauth2-talkdesk/releases)
[![Software License](https://img.shields.io/badge/license-MIT-brightgreen.svg?style=flat-square)](LICENSE.md)
[![Build Status](https://img.shields.io/travis/zingtree-inc/oauth2-talkdesk/master.svg?style=flat-square)](https://travis-ci.org/zingtree-inc/oauth2-talkdesk)
[![Total Downloads](https://img.shields.io/packagist/dt/zingtree-inc/oauth2-talkdesk.svg?style=flat-square)](https://packagist.org/packages/zingtree-inc/oauth2-talkdesk)

This package provides Talkdesk OAuth 2.0 support for the PHP League's [OAuth 2.0 Client](https://github.com/thephpleague/oauth2-client).

## Installation

To install, use composer:

```
composer require zingtree-inc/oauth2-talkdesk
```

## Usage

Usage is the same as The League's OAuth client, using `\Zingtree\OAuth2\Client\Provider\Talkdesk` as the provider.

### Authorization Code Flow

```php
$provider = new Zingtree\OAuth2\Client\Provider\Talkdesk([
    'clientId'          => '{talkdesk-client-id}',
    'clientSecret'      => '{talkdesk-client-secret}',
    'redirectUri'       => 'https://example.com/callback-url',
    'subdomain'         => 'your-talkdesk-subdomain',
]);
```
For further usage of this package please refer to the [core package documentation on "Authorization Code Grant"](https://github.com/thephpleague/oauth2-client#usage).

### Update and read subdomain after configuration

```php
$currentSubdomain = $provider->getSubdomain();
$newSubdomain = $currentSubdomain . '-v2';
$provider->setSubdomain($newSubdomain);
```
The provider will not complete configuration if a subdomain is not provided and updating the subdomain will silently fail if the value provided does not return truthy from `empty()`.

## Testing

``` bash
$ ./vendor/bin/phpunit
```

## Contributing

Please see [CONTRIBUTING](https://github.com/zingtree-inc/oauth2-talkdesk/blob/master/CONTRIBUTING.md) for details.


## Credits

- [Ryan Hoshor](https://github.com/russianryebread)
- [All Contributors](https://github.com/zingtree-inc/oauth2-talkdesk/contributors)


## License

The MIT License (MIT). Please see [License File](https://github.com/zingtree-inc/oauth2-talkdesk/blob/master/LICENSE) for more information.
