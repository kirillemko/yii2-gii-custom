Yii2 Custom model generator
=========================


Installation
------------

The preferred way to install this extension is through [composer](http://getcomposer.org/download/).

Either run

```
composer require kirillemko/yii2-gii-custom
```

or add

```
"kirillemko/yii2-gii-custom": "*"
```

to the require section of your composer.json.


Использование
-----
Этот генератор моделей генерирует два файла модели.
1. Это классический файл модели, но лежащий в папке generated
2. Пустая модель, унаследованная от той, которая в папке generated

Это позволяет вручную вносить изменения в модель наследка. А когда таблица в БД изменится, просто перегенерировать модель в папке generated, не потеряв изменения

Для использования зарегистрировать генератор в gii
```
'modules' => [
    'gii' => [
        'class' => 'yii\gii\Module',
        'generators' => [
            'customModel' => [
                'class' => 'kirillemko\gii\model\Generator',
                'generateCINamespace' => true
            ],
        ],
    ],
],
```

Из консоли генератор можно вызвать вот так
```
vendor\kirillemko\yii-ci-integration\src\yii gii/customModel --tableName=pm_kpi_groups --modelClass=
KpiGroups --ns=app\domain\kpi
```

Или сгенерировать по маске имени таблиц
```
./yii gii/customModel --tableName=uni* --ns=app\\domain\\unit\\models
```


Credits
-------

Authors: Kirill Emelianenko

Email: kirill.emko@mail.ru

