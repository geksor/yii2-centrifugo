# Yii2 Centrifugo Component
There is a wrapper for [Centrifugo](https://github.com/centrifugal/centrifugo) client based on [PHPCent](https://github.com/centrifugal/phpcent)
## Installation
Run command in shell
```shell
> composer require geksor/yii2-centrifugal "dev-master"
```
or add this line in to the `require` section of the `composer.json` file in your project 
```json
"geksor/yii2-centrifugal": "dev-master"
```

## Setup
Add into your config file as following
```php
'components' => [
	...
	'centrifugo' => [
		'class'  => 'yii2\centrifugo\Client',
		'host'   => 'http://localhost:8000',
		'secret' => 'very-long-secret-key',
		'apiKey' => 'very-long-api-key',
		// also you can specify your own transport class as below
		'transport' => [
			'class' => 'your\transport\ClassName',
			...
		]
	],
	...
]
```

## Usage
```php
Yii::$app->centrifugo->publish('test', ['message' => 'hello world']);
```
