---
slug: laravel9模型关联
title: laravel9模型关联
authors: [singi]
tags: [laravel, 模型关联]
---

## 一对一关联

### 表结构

用户表，头像表

```text
users
id
nickname

avatars
id
user_id
```

### 定义模型

```php
namespace App\Models;

use Illuminate\Database\Eloquent\Model;

class User extends Model
{
    public function avatar()
    {
        return $this->hasOne(Avatar::class);
    }
}
```

```php
namespace App\Models;

use Illuminate\Database\Eloquent\Model;

class Avatar extends Model
{
    public function user()
    {
        return $this->belongsTo(User::class);
    }
}
```

<!-- truncate -->

## 一对多关联

### 表结构

用户表（同上）， 订单表

```text
orders
id
user_id
no
title
```

### 定义模型

```php
namespace App\Models;

use Illuminate\Database\Eloquent\Model;

class User extends Model
{
    public function orders()
    {
        return $this->hasMany(Order::class);
    }
}
```

```php
namespace App\Models;

use Illuminate\Database\Eloquent\Model;

class Order extends Model
{
    public function user()
    {
        return $this->belongsTo(User::class);
    }
}
```
