---
slug: laravel12-demo
title: laravel12的示例
authors: [singi]
tags: [laravel]
---

## 在`WSL`中安装`laravel12`

```shell
# 安装编译PHP的依赖
sudo apt install -y autoconf build-essential libssl-dev libcurl4-openssl-dev libxml2-dev libzip-dev libonig-dev bison flex libgd-dev libfreetype6-dev libpng-dev re2c libpq-dev

# 安装php8.5
mise use -g php@8.5

# 安装laravel cli
composer global require laravel/installer

# 初始化项目
laravel new laravel12-demo

# 本地开发
composer run dev
```

> 本地开发支持前端代码热更新，非常好。

访问 http://localhost:8000/ ,如下图：

![首页](/static/img/laravel12-demo/index.png)

## 使用`frankenphp`运行

```shell
# 安装frankenphp
curl https://frankenphp.dev/install.sh | sh

# 安装caddy
curl -sS https://webi.sh/caddy | sh

# 通过 Laravel Octane 运行
composer require laravel/octane
php artisan octane:install --server=frankenphp
php artisan octane:frankenphp
```

> 注意 http://127.0.0.1:8000/ 无法使用，需要访问 http://localhost:8000/

> 服务器如果遇到性能问题，可以优先考虑这种运行方式。
