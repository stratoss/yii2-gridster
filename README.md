Gridster.js widget for Yii2
===========================
This extension provides the [Gridster.js](https://github.com/ducksboard/gridster.js) integration for the Yii2 framework.

[![Latest Stable Version](https://poser.pugx.org/fedemotta/yii2-gridster/v/stable)](https://packagist.org/packages/fedemotta/yii2-gridster) [![Total Downloads](https://poser.pugx.org/fedemotta/yii2-gridster/downloads)](https://packagist.org/packages/fedemotta/yii2-gridster) [![Latest Unstable Version](https://poser.pugx.org/fedemotta/yii2-gridster/v/unstable)](https://packagist.org/packages/fedemotta/yii2-gridster) [![License](https://poser.pugx.org/fedemotta/yii2-gridster/license)](https://packagist.org/packages/fedemotta/yii2-gridster)

Installation
------------

The preferred way to install this extension is through [composer](http://getcomposer.org/download/).

Either run

```
php composer.phar require --prefer-dist stratoss/yii2-gridster "*"
```

or add

```
"stratoss/yii2-gridster": "*"
```

to the require section of your `composer.json` file.

Usage
-----
Use Gridster.js as any other other Yii2 widget.

```php
use stratoss\gridster\Gridster;
```

```php
$gridster = Gridster::begin([
    'options'=>['class'=>'gridster'],
    'clientOptions'=>[
        'widget_margins'=> [10, 10],
        'widget_base_dimensions'=> [140, 140],
        'autogrow_cols'=> false,
        'resize'=>['enabled'=>true]
    ]
]);?>

<?= $gridster->beginWidget([
        'data-row'=>"1", 'data-col'=>"1", 'data-sizex'=>"5", 'data-sizey'=>"2",
    ]);
?>
    <header>Some text</header>
    The widget content
<?=$gridster->endWidget();?>

<?=$gridster->beginWidget([
        'data-row'=>"1", 'data-col'=>"1", 'data-sizex'=>"4", 'data-sizey'=>"1",
    ]);
?>
    <header>Some other text</header>
    The other widget content
<?=$gridster->endWidget();?>

<?php 
Gridster::end();
```

You can also use Gridster.js in the JavaScript layer of your application. To achieve this, you need to include Gridster as a dependency of your Asset file.

```php
public $depends = [
...
'stratoss\gridster\GridsterAsset',
...
];
```
