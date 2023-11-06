![Logo](https://github.com/Nakunai/TcBlog/blob/main/Web/pictures/logo.png?raw=true)

A blog project that I made in 2018 as part of my training. (4th project)
The goal was to create a personal blog with a user management system. I also choose to develop a custom framework.

## 📝 Requirements

- PHP 7
- MySQL

**This project use PSR-4 autoloading**

## 📕 Libs

- Bootstrap
- JQuery

The project use **Blog Home** Boostrap template.

## 🔧 Installation

1. Clone project

```bash
  git clone https://github.com/Nakunai/TcBlog.git
```

2. Install dependencies

```bash
  composer install
```

3. Use this template to create file **config.xml** in **App/Config**:

```xml
<?xml version="1.0" encoding="utf-8" ?>
<definitions>
    <!-- Database -->
    <define var="db_host" value="yourHost"/>
    <define var="db_name" value="yourDbName"/>
    <define var="db_username" value="yourDbUsername"/>
    <define var="db_password" value="yourDbPassword"/>
    <!---->
    <!-- SMTP Server -->
    <define var="username_smtp" value="yourSmtpUserName"/>
    <define var="password_smtp" value="yourSmtpPassword"/>
    <define var="domain_smtp" value="yourSmtpDomain"/>
    <define var="port_smtp" value="youSmtpPort"/>
    <!---->
    <!-- Others -->
    <define var="private_captcha_key" value="yourPrivateCaptchaKey"/>
    <define var="contact_email" value="yourContactEmail"/>
    <!---->
</definitions>
```

If you use captcha, change captcha public key in **app.xml**.

4. Create a file .htaccess in **/Web** and you can config simple in this style :

```apacheconf 
RewriteEngine On

RewriteCond %{REQUEST_FILENAME} !-f

RewriteRule ^(.*)$ index.php [QSA,L]
```

5. Import **tcBlog.sql** file to create table with demo data.
6. Create cron and script

For protect brute force attack, this project use cron, you can create this with : 

```bash
crontab -e
```

And you can write your cron in this style for execute a script all 24h : 

```bash
* * */1 * * php /path/to/your/file.php
```

For finish create your simply script in this style and complete :

```bash
$bdd = new PDO('mysql:host=yourDbHost;dbname=yourDbName;', 'yourDbUsername', 'yourDbPassword');

$bdd->exec('DELETE FROM connexion');</pre>
```


