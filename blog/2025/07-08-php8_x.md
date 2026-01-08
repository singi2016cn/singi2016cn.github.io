---
slug: php8_x
title: php8.x 常用新特性
authors: [singi]
tags: [php8, feature]
---

## [php8.0](https://www.php.net/releases/8.0/zh.php)

### 命名参数

- 仅仅指定必填参数，跳过可选参数。
- 参数的顺序无关、自己就是文档（self-documented）

php7

```php
htmlspecialchars($string, ENT_COMPAT | ENT_HTML401, 'UTF-8', false);
```

<!-- truncate -->

php8

```php
htmlspecialchars($string, double_encode: false);
```

### Match 表达式

- Match 是一个表达式，它可以储存到变量中亦可以直接返回。
- Match 分支仅支持单行，它不需要一个 break; 语句。
- Match 使用严格比较。

php7

```php
switch (8.0) {
  case '8.0':
    $result = "Oh no!";
    break;
  case 8.0:
    $result = "This is what I expected";
    break;
}
echo $result;
//> Oh no!
```

php8

```php
echo match (8.0) {
  '8.0' => "Oh no!",
  8.0 => "This is what I expected",
};
```

### Nullsafe 运算符

现在可以用新的 nullsafe 运算符链式调用，而不需要条件检查 null。 如果链条中的一个元素失败了，整个链条会中止并认定为 Null。

php7

```php
$country =  null;
if ($session !== null) {
  $user = $session->user;
  if ($user !== null) {
    $address = $user->getAddress();

    if ($address !== null) {
      $country = $address->country;
    }
  }
}
```

php8

```php
$country = $session?->user?->getAddress()?->country;
```
