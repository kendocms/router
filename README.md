<!-- markdownlint-disable no-inline-html -->
<p align="center">
  <br><br>
  <img src="https://leafphp.netlify.app/assets/img/leaf3-logo.png" height="100"/>
  <br>
</p>

<h1 align="center">Fork of Leaf Router</h1>

<p align="center">
	<a href="https://packagist.org/packages/leafs/router"
		><img
			src="https://poser.pugx.org/leafs/router/v/stable"
			alt="Latest Stable Version"
	/></a>
	<a href="https://packagist.org/packages/leafs/router"
		><img
			src="https://poser.pugx.org/leafs/router/downloads"
			alt="Total Downloads"
	/></a>
	<a href="https://packagist.org/packages/leafs/router"
		><img
			src="https://poser.pugx.org/leafs/router/license"
			alt="License"
	/></a>
</p>
<br />
<br />

Leaf router is the core routing engine which powers the Leaf PHP framework. Leaf router is now served as a serve-yourself module which can even be used outside the Leaf ecosystem.

**Leaf Router is still built into Leaf Core and doesn't need to be installed separately.**

## Installation

You can easily install Leaf using [Composer](https://getcomposer.org/).

```bash
composer require leafs/router
```

## Basic Usage

If you are using leaf router with Leaf, you can build your leaf apps just as you've always done:

```php
<?php
require __DIR__ . "vendor/autoload.php";

// GET example
app()->get("/", function () {
  response()->json([
    "message" => "Welcome!"
  ]);
});

// MATCH example
app()->match("GET", "/test", function () {
  response()->json([
    "message" => "Test!"
  ]);
});

app()->run();
```

If however, you are using leaf router outside of the leaf framework, you simply need to call these methods on the `Leaf\Router` object:

```php
<?php

use Leaf\Router;

require __DIR__ . "vendor/autoload.php";

// GET example
Router::get("/", function () {
  echo json_encode([
    "message" => "Welcome!"
  ]);
});

// MATCH example
Router::match("GET", "/test", function () {
  echo json_encode([
    "message" => "Test!"
  ]);
});

Router::run();
```
