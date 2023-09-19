# Les 2

## create new project

- create new project via terminal (composer has to be installed)

    ```bash
    composer create-project laravel/laravel example-app
    ```

- Open project in PHPStorm

    ```bash
    php artisan serve
    ```

## route (and first view)

- Open `web.php`
- Explain first route.
- Create about us route, with view.
    - First create route without the page.

    ```php
    Route::get('/about-us', function() {
        return 'About us';
    });
    ```

- Show return with HTML.
- replace return with *`return* view('about-us');`
- create view through context menu
- show linking to view (CMD + Click). Add tag and use lorem + tab.

## Create new Controller

- Open the terminal

    ```bash
    php artisan make:controller
    ```

  ![Use Upper Camel Case for the name because this is a Class file.](../images/controller-name.png)
    *Use Upper Camel Case for the name because this is a Class file.*

- *AboutUsController*
- Choose **Empty** controller.

**Edit AboutUsController**

- Open /app/Https/Controllers/AboutUsController
- Create index() method
- return ‘Test’
- Create route `Route::get('/test', [AboutUsController::*class*, 'index']);`

## **Create resource Controller**

- in terminal `php artisan make:controller`
- name: *ProductController*
- type: choose **Resource**
- model **empty** (for now)

  Alter index method

    ```php
    public function index()
    {
        return view('products.index');
    }
    ```

- Create a view and add HTML (ALT + Enter)
- Go to [localhost:8000/products](http://localhost:8000/products) *(why does it show a 404?)*

  **Add resource routes**

    ```php
    Route::resource('products', ProductController::class);
    ```


## **Add parameter to route**

If you want to pass extra information through a route like: https://localhost:8000/products/macbook, where "macbook" is 
the extra information you want to pass. You can do this by adding a parameter to the route.

- create route with `{ }` for query string parameters
    ```php
    Route::get('products/{name}', [ProductController::class, 'show']);
    ```
- Create the method with the parameter with the same parameter name

    ```php
    public function show($name) {
            return view('products.show', compact('name'));
        }
    ```

- Show the name variable in the view

    ```html
    <body>
        <h2>Welkom {{$name}}</h2>
    </body>
    ```


Resource routes have [parameters](https://laravel.com/docs/10.x/controllers#actions-handled-by-resource-controller) build in by default

## Laravel plugin

Tijdens de ontwikkeling van het project is het erg fijn om de **Laravel Idea plugin** te gebruiken. Deze moet je apart installeren in PHPStorm en als student kun je deze gratis gebruiken zolang je een student license hebt.

Om deze te installeren ga je naar de Settings (**PhpStorm | Settings** voor macOS of **File | Settings** voor Windows)

Klik op ****************Plugins.**************** Klik in het midden op **Marketplace** en zoek op “*Laravel”*

Klik op Install bij de Laravel Idea plugin.

![plugins](../images/plugins.png)

Wanneer je in het bezit bent van een [Jetbrains account met student license](https://www.jetbrains.com/shop/eform/students/), heb je ook gratis toegang tot deze plugin. Je zal het alleen wel moeten activeren.

Bij de installatie van de plugin zie je ook de link naar de [Plugin Homepage](https://plugins.jetbrains.com/plugin/13441-laravel-idea/pricing#edition=personal&tabs). Zorg dat je ingelogd bent op de webpagina met je Jetbrains account. Klik op de blauwe GET button of scroll naar beneden. Naast de knop met *For individual use / For organisation* zie je een dropdown met *Discounts available*. Kies hier voor de optie *For students.*

Hierna zie je dat de yearly subscription gratis wordt. En klik hier op apply.

![plugin payment](../images/plugin-payment.png)

Hierna kan je in PHPStorm op *Refresh* klikken bij de plugin (of PHPStorm opnieuw opstarten). De plugin is nu geactiveerd.