aws-sdk-wrapper
===============

Simple framework wrapper for Amazon's AWS SDK for PHP 5

Here is simple example on how to check e-mail verification status using Amazon's Simple Email Service with this wrapper:

```php
<?php
use \Exception;
use \Library\Amazon;
use \Aws\Common\Exception\ServiceResponseException;

$amazon = new Amazon();
$client = $amazon->get('ses');

try {
  $response = $client->getIdentityVerificationAttributes(
		array(
			'Identities' => array(
				'something@gmail.com'
			)
		)
	);

	print_r($response->getAll());
} catch (ServiceResponseException $exception) {
	print $exception->getMessage();
}
```

Read more: http://alekseykorzun.com/post/44203912088/simple-framework-wrapper-for-amazons-aws-sdk-for-php-5

