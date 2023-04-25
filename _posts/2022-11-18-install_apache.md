---
title: Install Apache WebServer
date: 2022-11-18 3:00:00 -0500
categories: [Linux]
tags: [linux,apache,httpd,jekyll,html]
---

## Install Apache WebServer (httpd)

### Links

[Linuxhint Article](https://linuxhint.com/install-configure-apache-web-server-ubuntu-22-04/)

```terminal
sudo apt install apache2
```

### Firewall (optional if hosted internally.  Port will be open by default as fw is disabled by default)

```terminal
sudo ufw enable
```

```terminal
sudo ufw app list
```

```terminal
sudo ufw allow 'Apache Full'
```

```terminal
sudo ufw status
```

### Check Status

```terminal
systemctl status apache2
```

### Setup Virtual Host File (enable site)

Create root (website files) directory in `/var/www/mynewdirectoryhere`

Chown it!
```terminal
sudo chown -R www-data:www-data /var/www/example.com
```

Create new host file:
```terminal
sudo nano /etc/apache2/sites-available/example.com.conf
```

In the opened virtual host file, add the following lines of code. Also, you have to replace the information related to “ServerName”, “ServerAlias”, and “DocumentRoot” according to your settings:

```terminal
<VirtualHost *:80>

ServerAdmin admin@localhost

ServerName example.com

ServerAlias www.example.com

DocumentRoot /var/www/example.com

ErrorLog ${APACHE_LOG_DIR}/error.log

CustomLog ${APACHE_LOG_DIR}/access.log combined

</VirtualHost>
```

Execute the following “a2ensite” command for enabling the created virtual host file:

```terminal
sudo a2ensite example.com.conf
```

Then disable the default configuration file:

```terminal
sudo a2dissite 000-default.conf
```
Restart apache

```terminal
sudo systemctl restart apache2
```
Error Testing:

```terminal
sudo apache2ctl configtest
```


> This is a "tip box"
{: .prompt-tip }

> This is a "info box"
{: .prompt-info }

> This is a "warning box"
{: .prompt-warning }

> This is a "danger box"
{: .prompt-danger }