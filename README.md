math-captcha
======================
виджет math-captcha

Installation
------------

The preferred way to install this extension is through [composer](http://getcomposer.org/download/).

Either run

```
php composer.phar require --prefer-dist lesha724/yii2-math-captcha "*"
```

or add

```
"lesha724/yii2-math-captcha": "*"
```

to the require section of your `composer.json` file.


Usage
-----

Once the extension is installed, simply use it in your code by  :

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
                //don`t set foreColor and backColor (they is random color)
                //more options http://www.yiiframework.com/doc-2.0/yii-captcha-captchaaction.html
            ],
        ];
    }
}

```
