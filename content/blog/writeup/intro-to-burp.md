---
title: IntroToBurp - WriteUp
date: 2024-08-06
authors:
  - name: YI-XUAN, CHEN
    id: tntrenjin
    image: https://avatars.githubusercontent.com/u/45209009
tags:
  - picoCTF 2024
  - writeup
  - Easy
  - Web Exploitation
---

<!--more-->

**使用工具或套件**

- Burp Suite

---

### 打開 Burp Suite

切換到 `Proxy` -> `Intercept`，然後點選 `Open browser`，用它的瀏覽器去開網站

### 打開網站

開啟後，會看到以下這個表單，表單內容隨便填就好
![](./intro-to-burp//image.png)

### OTP

下個畫面會導向到 OTP 驗證，內容一樣隨便填，然後把 Burp Suite 的 Intercept 切成 on 之後送出表單
![](./intro-to-burp/image-1.png)

在 Burp Suite 攔截封包，然後刪除第七行的 `otp=123`，再按 Forward 後

```text{linenos=table,hl_lines=[7],linenostart=1}
...
Referer: http://titan.picoctf.net:52900/dashboard
Accept-Encoding:gzip,deflate,br
Cookie: session=
Connection: keep-alive

otp=123
```

回到瀏覽器就會看到
![](./intro-to-burp/image-2.png)

### Flag

> picoCTF{#0TP_Bypvss_SuCc3$S_9090d63c}
