---
title: 用 certbot 自动生成 ssl 证书
date: 2017-12-04 12:12:10
category:
- Develop
tags:
- certbot
- ssl
- nginx
---

本文内容以 nginx 为例。

### 安装 certbot

#### Linux

```bash
sudo apt update
sudo apt install certbot
```

#### Mac

```bash
brew install certbot
```

### 生成证书

```bash
sudo certbot --nginx
```

### 选择域名

certbot 会根据你的 nginx 配置列出所有域名，你可以根据变化选择生成 ssl 证书的域名
，也可以直接回车，为所有服务器上所有域名生成证书。

```
Saving debug log to /var/log/letsencrypt/letsencrypt.log
Plugins selected: Authenticator nginx, Installer nginx

Which names would you like to activate HTTPS for?
-------------------------------------------------------------------------------
1: your.domain.one
2: your.domain.two
-------------------------------------------------------------------------------
Select the appropriate numbers separated by commas and/or spaces, or leave input
blank to select all options shown (Enter 'c' to cancel):
```

### 是否覆盖证书

如果证书已经存在，certbot 会让你选择是尝试重新安装还是续约：

```
What would you like to do?
-------------------------------------------------------------------------------
1: Attempt to reinstall this existing certificate
2: Renew & replace the cert (limit ~5 per 7 days)
-------------------------------------------------------------------------------
Select the appropriate number [1-2] then [enter] (press 'c' to cancel):
```

### 是否跳转

证书生成成功，certbot 询问是否所有 http 链接自动跳转到 https 链接，按自己需要选
择。

```
Please choose whether or not to redirect HTTP traffic to HTTPS, removing HTTP access.
-------------------------------------------------------------------------------
1: No redirect - Make no further changes to the webserver configuration.
2: Redirect - Make all requests redirect to secure HTTPS access. Choose this for
new sites, or if you're confident your site works on HTTPS. You can undo this
change by editing your web server's configuration.
-------------------------------------------------------------------------------
Select the appropriate number [1-2] then [enter] (press 'c' to cancel):
```

### 成功信息

```
IMPORTANT NOTES:
- Congratulations! Your certificate and chain have been saved at:
  /etc/letsencrypt/live/YOUR.DOMAIN/fullchain.pem
  Your key file has been saved at:
  /etc/letsencrypt/live/YOUR.DOMAIN/privkey.pem
  Your cert will expire on 2018-03-04. To obtain a new or tweaked
  version of this certificate in the future, simply run certbot again
  with the "certonly" option. To non-interactively renew *all* of
  your certificates, run "certbot renew"
- If you like Certbot, please consider supporting our work by:

  Donating to ISRG / Let's Encrypt:   https://letsencrypt.org/donate
  Donating to EFF:                    https://eff.org/donate-le
```
