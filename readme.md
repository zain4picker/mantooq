# Laravel Arabic Numbers
Laravel package to handel ANY THING about our Amazing 💝 Arabic Numbers Functions { كل ما يهم محبي لارافيل واستخدام الأرقام العربية مثل منطوق الأرقام والمبالغ المالية والعكس و عرض الأرقام بالعربية والعكس }

![Packagist License](https://img.shields.io/packagist/l/zain4picker/mantooq) ![Packagist Version](https://img.shields.io/packagist/v/zain4picker/mantooq) ![GitHub release (latest by date)](https://img.shields.io/github/v/release/zain4picker/mantooq?color=red)  [![Total Downloads](https://poser.pugx.org/zain4picker/mantooq/downloads)](//packagist.org/packages/zain4picker/mantooq) ![Packagist Stars](https://img.shields.io/packagist/stars/zain4picker/mantooq?color=yellow)
## كل ما يهم محبي لارافيل واستخدام الأرقام العربية مثل منطوق الأرقام والمبالغ المالية والعكس و عرض الأرقام بالعربية والعكس 
## Installation for all Laravel Versions 🥳
1- You can install the package via composer:

    composer require zain4picker/mantooq

2- You must register the service provider in your `config/app.php` file:

    'providers' => [
        // ...
        Picker\ArabicNumbers\ArabicNumbersServiceProvider::class,
    ];

3- You must register the Middleware in your `App\Http\Kernel` file:

    protected $middleware = [
        // ...
        Picker\ArabicNumbers\Http\Middleware\ConvertArabicDigitsToEnlishMiddleware::class
    ];

Now any request have arabic indic [١،٢،٣،٤،٥،٦،٧،٨،٩،٠] Numbers will Translated 🥳 to [1,2,3,4,5,6,7,8,9,0] 

## Excepting Fields 
If you want to except any field from transforming request, Just add the fields you want to except them in the Middleware `ConvertArabicDigitsToEnlishMiddleware::class` :

	        /**
             * The fields that should not be Transformed.
             *
             * @var array
             */
            protected $except = [
                'password', 'password_confirmation' ,'numbers','count'
            ];

## Usage
![Arabic Numbers](imags/numbers.png)

##   منطوق المبالغ المالية باللغة العربية الفصحى مثل 123 => { مئة و ثلاثة و عشرون ريالًا فقط لا غير } 
You can simply get Mantooq of The int Money amount directly in Arabic idioms 
```php
    use Picker\ArabicNumbers\Numbers;

    $number = 64.56;
    Numbers::MantooqMoney($number); //It will Give SAR by default

    // RESULT {  أربعة و ستون ريالًا و ست و خمسون هللة فقط لا غير }


    [OR]


    $value = 64.56;
    Numbers::MantooqMoney($value,'EGP'); //You can pass $currency as the second @param

    // RESULT {  أربعة و ستون جنيهًا و ست و خمسون قرش فقط لا غير }
```

##   منطوق الأرقام باللغة العربية الفصحى مثل 64 => { أربعة و ستون } 
You can simply get Mantooq of The int Value directly in Arabic idioms 
```php
    use Picker\ArabicNumbers\Numbers;

    $number = 64;
    Numbers::MantooqNumber($number);

    // RESULT {  أربعة و ستون }
```
## إستخراج الأرقام من المنطوق باللغة العربية للأرقام وليس للمبالغ 😉 مثل { أربعة و ستون } => 64
You can simply Reverse Mantooq in Arabic idioms to The int Number directly 
```php
    use Picker\ArabicNumbers\Numbers;

    $string = "أربع و ستون فاصلة ست و خمسون";
    Numbers::NumberFromString($number);

    // RESULT 64.56
```
## عرض الأرقام العربية بدل الأرقام الإنجليزية والعكس حسب رغبة المستخدم 657 =>  ٦٥٧
You can simply Show Any Value in Arabic Digits Or English Digits
```php
    use Picker\ArabicNumbers\Numbers;

    $number = 64; // integar value
    Numbers::ShowInArabicDigits($number);

    // RESULT "٦٤.٥٦"


    [OR]


    use Picker\ArabicNumbers\Numbers;

    $value = "٦٤.٥٦"; // Can be Any Value STRING or INTEGAR
    Numbers::ShowInEnglishDigits($value);

    // RESULT "64.56"


    [EVEN 🥳 Any Value]


    use Picker\ArabicNumbers\Numbers;

    $value = "تاريخ اليوم : 22-10-2020"; // Can be Any Mix Value STRING with INTEGAR
    Numbers::ShowInArabicDigits($value);

    // RESULT {تاريخ اليوم : ٢٢-١٠-٢٠٢٠}
```
#### Give Me 💗 Cup of ☕️ Coffee here https://patreon.com/mohammadelkoumi
