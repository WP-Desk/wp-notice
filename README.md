[![pipeline status](https://gitlab.com/wpdesk/wp-notice/badges/master/pipeline.svg)](https://gitlab.com/wpdesk/wp-notice/pipelines) 
[![coverage report](https://gitlab.com/wpdesk/wp-notice/badges/master/coverage.svg?job=integration+test+lastest+coverage)](https://gitlab.com/wpdesk/wp-notice/commits/master) 
[![Latest Stable Version](https://poser.pugx.org/wpdesk/wp-notice/v/stable)](https://packagist.org/packages/wpdesk/wp-notice) 
[![Total Downloads](https://poser.pugx.org/wpdesk/wp-notice/downloads)](https://packagist.org/packages/wpdesk/wp-notice) 
[![Latest Unstable Version](https://poser.pugx.org/wpdesk/wp-notice/v/unstable)](https://packagist.org/packages/wpdesk/wp-notice) 
[![License](https://poser.pugx.org/wpdesk/wp-notice/license)](https://packagist.org/packages/wpdesk/wp-notice) 


WordPress Library to display notices in admin area.
===================================================

wp-notice is a simple library for WordPress plugins to display notices in admin area.

This library can display simple notices (error, warning, success, info) and dismissible notices.
It also handles dismiss functionality with AJAX requests.  

## Requirements

PHP 5.5 or later.

## Installation with composer

You can install the bindings via [Composer](http://getcomposer.org/). Run the following command:

```bash
composer require wpdesk/wp-notice
```

To use the bindings, use Composer's [autoload](https://getcomposer.org/doc/01-basic-usage.md#autoloading):

```php
require_once 'vendor/autoload.php';
```

## Manual installation

If you do not wish to use Composer, you can [download the latest release](https://gitlab.com/wpdesk/wp-notice/-/jobs/artifacts/master/download?job=library). Then, to use the Notices, include the init.php file.

```php
require_once('/path/to/wp-desk/wp-notice/init.php');
```

## Getting Started

### Simple usage looks like

```php
$notice = wpdesk_wp_notice('Notice text goes here');

// Is equivalent to:
$notice = WPDeskWpNotice('Notice text goes here');

// Is equivalent to:
$notice = \WPDesk\Notice\Factory::notice('Notice text goes here');

// Is equivalent to:
$notice = new \WPDesk\Notice\Notice('Notice text goes here'); 
```

Notice must be used before WordPress action `admin_notices`. WordPress admin actions order is listed [here](https://codex.wordpress.org/Plugin_API/Action_Reference#Actions_Run_During_an_Admin_Page_Request).

## Permanent dismissible notices

### AJAX handler

To use permanent dismissible notices AJAX handler must be created and hooks initialized:

```php
wpdesk_init_wp_notice_ajax_handler();

// Is equivalent to:
( new \WPDesk\Notice\AjaxHandler() )->hooks();
```

### Displaying 

To display permanent dismissible notice:

```php
wpdesk_permanent_dismissible_wp_notice( 'Notice text goes here', 'notice-name' );

// Is equivalent to
new PermanentDismissibleNotice( 'Notice text goes here', 'notice-name' );
```
