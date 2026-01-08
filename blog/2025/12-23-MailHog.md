---
slug: MailHog
title: MailHog使用指南
authors: [singi]
tags: [mise, MailHog]
---

## 安装以及使用

```shell
# 安装
go install github.com/mailhog/MailHog@latest

# 使用
MailHog
```

> 然后访问浏览器地址：http://0.0.0.0:8025/

> 邮件发送端口是：1025

更多请参考：[文档](https://github.com/mailhog/MailHog)

<!-- truncate -->

## 测试发送邮件

```shell
# 安装发送邮件服务
go install github.com/mailhog/mhsendmail@latest
# 发送测试邮件
mhsendmail test@mailhog.local <<EOF
From: App <app@mailhog.local>
To: Test <test@mailhog.local>
Subject: Test message

Some content!
EOF
```

更多请参考：[文档](https://github.com/mailhog/mhsendmail)
