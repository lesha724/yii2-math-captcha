math-captcha
======================
виджет math-captcha

![Пример](https://raw.githubusercontent.com/lesha724/yii2-math-captcha/master/img/example.PNG)

Установка
------------

Предпочтительным способом установки этого расширения является [composer](http://getcomposer.org/download/).

Выполните

```
php composer.phar require --prefer-dist lesha724/yii2-math-captcha "*"
```

или добавьте

```
"lesha724/yii2-math-captcha": "*"
```

в блок require в вашем `composer.json` файле.


Использование
-----

Как только расширение будет установлено, просто используйте его в своем коде  :

```php
use yii\web\Controller;

class SiteController extends Controller
{
    public function actions()
    {
        return [
            ...
            'captcha' => [
                'class' => 'lesha724\MathCaptcha\MathCaptchaAction',
                //'imageLibrary'=>'imagick', only 'gd' and 'imagick' 
                'fixedVerifyCode' => YII_ENV_TEST ? '42' : null,
                //не задавайте значение foreColor и backColor (они заполняться случайными цветами)
                //остльные опции http://www.yiiframework.com/doc-2.0/yii-captcha-captchaaction.html
            ],
        ];
    }
}

```

```php

<?php $form = ActiveForm::begin([]); ?>

....

<?= $form->field($model, 'verifyCode')->widget(\yii\captcha\Captcha::className(), [
	'template' => '{image} {input}',
]) ?>

....

<?php ActiveForm::end(); ?>

```
