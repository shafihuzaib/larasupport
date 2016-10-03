Larasupport Package
====================

[![Package for Lumen](https://img.shields.io/badge/Package%20for%20-Lumen-blue.svg?style=flat-square)](https://github.com/shafihuzaib/larasupport)
[![Latest Version](https://img.shields.io/github/release/shafihuzaib/larasupport.svg?style=flat-square)](https://github.com/shafihuzaib/larasupport/releases)
[![Software License](https://img.shields.io/badge/license-MIT-brightgreen.svg?style=flat-square)](LICENSE)
[![Total Downloads](https://img.shields.io/packagist/dt/shafihuzaib/larasupport.svg?style=flat-square)](https://packagist.org/packages/shafihuzaib/larasupport)


> Laravel Support for Lumen: Adds missing helpers that are not being made to the core of Lumen. Lets you use Laravel Packages in Lumen.
>
> There are some helper functions that are available in core of Laravel framework which are being used in Laravel Packages. Now because of these helpers missing in core of the Lumen, You won't be able to use those amazing Laravel Packages.
>
> I had submited PRs as well as created issue tickets in Lumen to add these helpers to the core but it got rejected with a reason to use Laravel instead. Just for Packages support i didn't want to use full-stack framework. There were few discussions about the same as well. Hence, This package to deal with this issue!

## Quick Start


### Installation

#### Install Through Composer

You can either add the package directly by firing this command

```
$ composer require shafihuzaib/larasupport:~1.0
```
	
Or add in the `require` key of `composer.json` file manually

```
"shafihuzaib/larasupport": "~1.0"
```

And Run the Composer update command

```
$ composer update
```

#### Add Service Provider

Add this service provider to your `bootstrap/app.php` file.

``` php
$app->register(Irazasyed\Larasupport\Providers\ArtisanServiceProvider::class);
```
Artisan Service Provider is an optional provider required only if you want `vendor:publish` command working.

And you're done! You can now start installing any Laravel Package out there.

## Available Methods
> These helpers can be used across your Lumen project, not only with Laravel Packages.

### Paths

#### public_path
Get the fully qualified path to the `public` directory. You can set env variable `PUBLIC_PATH` and it'll return the same instead of the default `public`.

#### config_path
Get the fully qualified path to the `config` directory (Mostly used with Laravel Packages).

#### database_path
Get the fully qualified path to the `database` directory (Mostly used with Laravel Packages).

#### app_path
Get the fully qualified path to the `app` directory.

### Artisan

#### vendor:publish
Artisan command to Publish any publishable assets from vendor packages (Required to get Laravel Packages working!).

```cli
php artisan vendor:publish
```
OR

```cli
php artisan vendor:publish --provider="Vendor\Providers\PackageServiceProvider" 
```

### Other

#### route_parameter

```php
route_parameter($name, $default = null)
```
Get a given parameter from the route.

#### elixir

If you're using Laravel Elixir in Lumen, Then this helper function will come handy when you want to include assets from your build directory. By default, it assumes your Elixir's build directory is `build` under public directory (The default is as per the Elixir's default config). If you use a custom build directory, then you can simply set env variable `ELIXIR_BUILD_PATH` with your custom directory path and it'll use the same instead of the default.

``` html
<link rel="stylesheet" href="{{ elixir('css/all.css') }}">

<script src="{{ elixir('js/app.js') }}"></script>
```

## Contributions

PRs are Welcome :)

## Additional information


Any issues, please [report here](https://github.com/irazasyed/larasupport/issues).

The methods have been ported from the core of Laravel framework and modified to fit the requirements.

## License

[MIT](LICENSE) © [Syed Irfaq R.](http://lk.gd/irazasyed)
