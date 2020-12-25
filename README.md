敏感信息打码处理类
-----------

## 编辑 `composer.json`

```json
{
  "repositories": [{
    "url": "git@github.com:amsterdan5/mask.git",
    "type": "git"
  }],
  "require": {
    "amsterdan/mask": "dev-main"
  }
}
```

## 使用方法
```php
<?php

use Amsterdan\Mask;

//对于非自动加载，请打开下面的注释
/**
spl_autoload_register(function ($class) {
    include 'src/' . str_replace('\\', '/', $class) . '.php';
});
*/

$str = '44528119991005005X';

echo Mask::formatIdCard($str) . PHP_EOL;

$str = '13800138000';

echo Mask::formatPhone($str) . PHP_EOL;

$str = '6222003602101234080';

echo Mask::formatBankCard($str) . PHP_EOL;

$str = '123456';

echo Mask::formatPassword($str) . PHP_EOL;

$str = '12345678@abc.com';

echo Mask::formatEmail($str) . PHP_EOL;

$data = [
    'id_card'     => '44528119991005005X',
    'idcard'      => '44528119991005005X',
    'identity_id' => '44528119991005005X',
    'idNumber'    => '44528119991005005X',
    'id_number'   => '44528119991005005X',
];

$data = Mask::format($data);

```
