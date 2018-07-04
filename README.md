<p align="center">
    <a href="https://sylius.com" target="_blank">
        <img src="https://demo.sylius.com/assets/shop/img/logo.png" />
    </a>
</p>

<h1 align="center">Admin Order Creation Plugin</h1>

<p align="center">This plugin allows to create an order in admin panel.</p>

## Installation

1. Require plugin with composer:

    ```bash
    composer require sylius/admin-order-creation-plugin
    ```

2. Import configuration:

    ```yaml
    imports:
        - { resource: "@SyliusAdminOrderCreationPlugin/Resources/config/app/config.yml" }
    ```

3. Import routing:

    ```yaml
    sylius_admin_order_creation:
        resource: "@SyliusAdminOrderCreationPlugin/Resources/config/app/routing.yml"
    ```

4. Add plugin class to your `AppKernel`:

    ```php
    $bundles = [
        new \FOS\JsRoutingBundle\FOSJsRoutingBundle(), //used by plugin
        new \Sylius\AdminOrderCreationPlugin\SyliusAdminOrderCreationPlugin(),
    ];
    ```

5. Copy templates from `vendor/sylius/admin-order-creation-plugin/src/Resources/views/SyliusAdminBundle/` 
   to `app/Resources/SyliusAdminBundle/views/`.

6. Copy migrations from `vendor/sylius/admin-order-creation-plugin/migrations/` 
   to your migrations directory and run `bin/console doctrine:migrations:migrate`.

7. Install `FOSJsRoutingBundle` assets:

    ```
    bin/console assets:install --symlink web
    ```

8. Clear cache:

    ```bash
    bin/console cache:clear
    ```
