yii2-gii
=

Installation
------------

The preferred way to install this extension is through [composer](http://getcomposer.org/download/).

Either run

```bash
composer require --dev m1roff/yii2-gii "^2.0"
```




Configure
-----
add this lines to main-local.php config

```php

if (!YII_ENV_TEST) {
    ...
    
    $config['bootstrap'][] = 'gii';
    $config['modules']['gii'] = [
        'class' => 'yii\gii\Module',
        'allowedIPs' => ['*'],
        'generators' => [ //here
            'model' => [ // generator name
                'class' => 'm1roff\gii\generators\model\Generator', // generator class
                'templates' => [ //setting for out templates
                    'myModel' => '@m1roff/gii/generators/model/default', // template name => path to template
                ]
            ],
            'crud' => [ // generator name
                'class' => 'm1roff\gii\generators\crud\Generator', // generator class
                'templates' => [ //setting for out templates
                    'myCrud' => '@m1roff/gii/generators/crud/default', // template name => path to template
                ]
            ],
        ],
    ];
}

```
