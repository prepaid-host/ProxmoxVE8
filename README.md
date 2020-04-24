ProxmoxVE API Client
====================

This **PHP 5.5+** library allows you to interact with your Proxmox server via API.

[![Build Status](https://travis-ci.org/ZzAntares/ProxmoxVE.svg?branch=master)](https://travis-ci.org/ZzAntares/ProxmoxVE)
[![Latest Stable Version](https://poser.pugx.org/zzantares/proxmoxve/v/stable.svg)](https://packagist.org/packages/zzantares/proxmoxve)
[![Total Downloads](https://poser.pugx.org/zzantares/proxmoxve/downloads.svg)](https://packagist.org/packages/zzantares/proxmoxve)
[![Latest Unstable Version](https://poser.pugx.org/zzantares/proxmoxve/v/unstable.svg)](https://packagist.org/packages/zzantares/proxmoxve)
[![License](https://poser.pugx.org/zzantares/proxmoxve/license.svg)](https://packagist.org/packages/zzantares/proxmoxve)

> I'm not actively maintaining this library anymore (I've left PHP behind) but **the API is pretty stable**, if it doesn't suit your needs take a look at the forks or better yet create a PR to add the things you're missing, if you're interested I can transfer the project to you.

**Looking for a PHP 5.3 library version?** Search through the [releases](https://github.com/lumaserv/ProxmoxVE/releases) one that fits your needs, I recommend using the [2.1.1](https://github.com/lumaserv/ProxmoxVE/releases/tag/v2.1.1) version.


Installation
------------

Recommended installation is using [Composer], if you do not have [Composer] what are you waiting?

In the root of your project execute the following:

```sh
$ composer require lumaserv/proxmoxve ~4.0.4
```

Or add this to your `composer.json` file:

```json
{
    "require": {
        "lumaserv/proxmoxve": "~4.0.4"
    }
}
```

Then perform the installation:
```sh
$ composer install --no-dev
```


Usage
-----

```php
<?php

// Require the autoloader
require_once 'vendor/autoload.php';

// Use the library namespace
use ProxmoxVE\Proxmox;

// Create your credentials array
$credentials = [
    'hostname' => 'proxmox.server.com',  // Also can be an IP
    'username' => 'root',
    'password' => 'secret',
];

// realm and port defaults to 'pam' and '8006' but you can specify them like so
$credentials = [
    'hostname' => 'proxmox.server.com',
    'username' => 'root',
    'password' => 'secret',
    'realm' => 'pve',
    'port' => '9009',
];

// Then simply pass your credentials when creating the API client object.
$proxmox = new Proxmox($credentials);

$allNodes = $proxmox->get('/nodes');

print_r($allNodes);
```


Sample output:

```php
Array
(
    [data] => Array
        (
            [0] => Array
                (
                    [disk] => 2539465464
                    [cpu] => 0.031314446882002
                    [maxdisk] => 30805066770
                    [maxmem] => 175168446464
                    [node] => mynode1
                    [maxcpu] => 24
                    [level] =>
                    [uptime] => 139376
                    [id] => node/mynode1
                    [type] => node
                    [mem] => 20601992182
                )

        )

)
```


Want to know more nifty tricks?
-------------------------------

Checkout our [wiki](https://github.com/ZzAntares/ProxmoxVE/wiki).

License
-------

This project is released under the MIT License. See the bundled [LICENSE] file for details.

[LICENSE]:./LICENSE
=======

Want to contribute?
--------------------

Thank you! Take a look at the [CONTRIBUTING], you could easily set up a development environment to get you started in no time!


[LICENSE]:./LICENSE
[CONTRIBUTING]:./CONTRIBUTING.md
>>>>>>> upstream/master
[PVE2 API Documentation]:http://pve.proxmox.com/pve-docs/api-viewer/index.html
[ProxmoxVE API]:http://pve.proxmox.com/wiki/Proxmox_VE_API
[Proxmox wiki]:http://pve.proxmox.com/wiki
[Composer]:https://getcomposer.org/
