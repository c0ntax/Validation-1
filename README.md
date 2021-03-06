Validation (Laravel 4 Package)
==========

*"The power of 'Respect Validation' on Laravel 4 Validation"*

### Required setup

In the **require** key of **composer.json** file add the following:

```php
"kennedytedesco/validation": "dev-master"
```

Run the Composer **update** comand:

```php
composer update
```

In your **config/app.php** add *'KennedyTedesco\Validation\ValidationServiceProvider'* to the end of the **'providers'** array:

```php
'providers' => array(
    ...
    ...
    'KennedyTedesco\Validation\ValidationServiceProvider',
),
```

## Supported rules (with examples) 

```php
// Rules
$rules = array(
    'cpf'               => 'cpf',
    'cnpj'              => 'cnpj',
    'cnh'               => 'cnh', // Carteira Nacional de Habilitação
    'minimum_age'       => 'minimumAge:20',
    'callback'          => 'callback:is_int',
    'charset'           => 'charset:ASCII',
    'consonant'         => 'consonant',
    'vowel'             => 'vowel',
    'alnum'             => 'alnum:-',
    'digit'             => 'digit',
    'alpha'             => 'alpha',
    'containsArray'     => 'contains:banana',
    'contains'          => 'contains:banana',
    'countryCode'       => 'countryCode',
    'creditCard'        => 'digit|creditCard',
    'domain'            => 'domain',
    'directory'         => 'directory',
    'FileExists'        => 'FileExists',
    'isFile'            => 'file',
    'endsWith'          => 'endsWith:banana',
    'equals'            => 'equals:banana',
    'even'              => 'even',
    'float'             => 'float',
    'graph'             => 'graph',
    'instance'          => 'instance:DateTime',
    'int'               => 'int',
    'json'              => 'json',
    'leapDate'          => 'leapDate:Y-m-d',
    'leapYear'          => 'leapYear',
    'arr'               => 'arr',
    'lowercase'         => 'lowercase',
    'macAddress'        => 'macAddress',
    'multiple'          => 'multiple:3',
    'negative'          => 'negative',
    'noWhitespace'      => 'noWhitespace',
    'notArray'          => 'arr|not',
    'nullValue'         => 'nullValue',
    'numeric'           => 'numeric',
    'object'            => 'object',
    'odd'               => 'odd',
    'perfectSquare'     => 'perfectSquare',
    'positive'          => 'positive',
    'primeNumber'       => 'primeNumber',
    'punct'             => 'punct',
    'readable'          => 'readable',
    'regex'             => 'regex:/5/',
    'roman'             => 'roman',
    'slug'              => 'slug',
    'space'             => 'space:b',
    'tld'               => 'tld', // Top Level Domain,
    //'uploaded'        => 'uploaded',
    'uppercase'         => 'uppercase',
    'version'           => 'version',
    'xdigit'            => 'xdigit', // Hexadecimal
    'writable'          => 'writable',
    'alwaysValid'       => 'alwaysValid',
    'bool'              => 'bool'       
);

// Data
$data = array(
    'cpf'               => '22205417118',
    'cnpj'              => '68518321000116',
    'cnh'               => '02650306461',
    'minimum_age'       => '10/10/1990',
    'callback'          => 20,
    'charset'           => 'acucar',
    'consonant'         => 'dcfg',
    'vowel'             => 'aeiou',
    'alnum'             => 'banana-123 ',
    'digit'             => '120129  21212',
    'alpha'             => 'banana',
    'containsArray'     => array('www', 'banana', 'jfk', 'http'),
    'contains'          => 'www banana jfk http',
    'countryCode'       => 'BR',
    'creditCard'        => '5555666677778884',
    'domain'            => 'google.com.br',
    'directory'         => __DIR__,
    'FileExists'        => __FILE__,
    'file'              => __FILE__,
    'endsWith'          => 'pera banana',
    'equals'            => 'banana',
    'even'              => 8,
    'float'             => 9.8,
    'graph'             => 'LKM@#$%4;',
    'instance'          => new Datetime(),
    'int'               => 9,
    'json'              => '{"file":"laravel.php"}',
    'leapDate'          => '1988-02-29',
    'leapYear'          => '1988',
    'arr'               => array('Brazil'),
    'lowercase'         => 'brazil',
    'macAddress'        => '00:11:22:33:44:55',
    'multiple'          => '9',
    'negative'          => '-10',
    'noWhitespace'      => 'laravelBrazil',
    'nullValue'         => null,
    'numeric'           => '179.9',
    'object'            => new stdClass(),
    'odd'               => 3,
    'perfectSquare'     => 25,
    'positive'          => 1,
    'primeNumber'       => 7,
    'punct'             => '&,.;[]',
    'readable'          => __FILE__,
    'regex'             => '5',
    'roman'             => 'VI',
    'slug'              => 'laravel-brazil',
    'space'             => '              b      ',
    'tld'               => 'com',
    //'uploaded'        => 'path to file',
    'uppercase'         => 'BRAZIL',
    'version'           => '1.0.0',
    'xdigit'            => 'abc123',
    'writable'          => __FILE__,
    'alwaysValid'       => '@#$_',
    'bool'              => is_int(2)
);

// Make the validation
$validator = \Validator::make($data, $rules);

// Result
if( $validator->fails() )
{
    // Print errors
    $messages = $validator->messages();            
    foreach ($messages->all() as $message) {
        echo '<li>'.$message.'</li>';
    }            
}
else
{
    // Success
    echo 'True.';
}
```

# Respect Validation

For more details on the rules:

https://github.com/Respect/Validation

Tks for Respect: **The most awesome validation engine ever created for PHP!**