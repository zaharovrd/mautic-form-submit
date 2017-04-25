# PHP library for submitting Mautic Form from 3rd party app

[![Software License][ico-license]](LICENSE.md)

Submitting a form can get handy if you want to process the data with your app, but you want to send them to Mautic too. Mautic can then run automated tasks triggered by the form submission. [Read more about it](https://medium.com/@jan_linhart/the-simplest-way-how-to-submit-a-form-data-to-mautic-1454d3afd005) in the original post.

## Install

### Via Composer

```bash
composer require escopecz/mautic-form-submit
```

## Usage

```php
require __DIR__.'/vendor/autoload.php';

$mautic = new \MauticFormSubmit\Mautic('https://mymautic.com');
$form = $mautic->getForm(342);
$result = $form->submit(
	[
		'f_email' => 'john@doe.email',
	]
);
```

- The integer passed to the `getForm()` method must be ID of the Mautic form.
- The array passed to the `submit()` method must be associative array of `['mautic_field_alias' => 'the_value']`.

For working example see the `examples` dir.

## License

The MIT License (MIT). Please see [License File](LICENSE.md) for more information.
