### Enable mod-rewrite

`sudo a2enmod rewrite`

### Mod-rewrite syntax

The basic Apache mod_rewrite syntax has the following parts:

`RewriteRule pattern substitution [flags]`

- **RewriteRule** – the directive of our rule.
- **Pattern** – this is a regex (Regular Expression) that matches what the user types in a browser.
- **Substitution** – The actual URL path that should be called by the Apache server.
- **Flag** – optional parameters that modify how the rules work..

### Create a sample .htaccess file

We will now create a sample ‘.htaccess’ file at the root of the default website to test mod_rewrite. To do this type the command below

`$ sudo nano /var/www/html/.htaccess`

Every mod_rewrite rules must be with the commands ‘RewriteEngine on’. So you need to type this at the top of the file.

`RewriteEngine on`

Next, we are going to rewrite a rule that redirects users to a ‘contact_us.html’ page if they request the URL http://ipaddress/contact_us

So we add the below rule:

`RewriteRule ^contact_us$ contact_us.html [NC]`

In the above rule, ‘contact_us’ is the pattern that should be matched and redirected to our substitution path ‘contact_us.html’. The command ‘[NC]’is a flag that tells Apache to make the rule case insensitive. ‘^’ indicates that we are matching any text after the server public IP address or domain name while ‘$’ signifies the end of the URL that we are matching.

So our complete ‘.htaccess’ a file should look like the text below:

```
RewriteEngine on
RewriteRule ^contact_us$ contact_us.html [NC]
```

Save the file by pressing CTRL+ X, Y, and Enter.

Next type the command below to create the contact_us.html page:

`$ sudo nano /var/www/html/contact_us.html`

Then, paste the HTML text below on the file:

```
<html>
        <head>
            <title>Contact our website</title>
        </head>
        <body>
            <h1>This is a contact us page</h1>
        </body>
    </html>
```

Save the file by pressing CTRL+ X, Y and Enter.
Now if you visit the path http://ipaddress/contact_us on a browser, Apache should serve you with the page ‘contact_us.html’ that we created like shown below:

*This is a contact us page*
* * *

/ ***Max Ostryzhko*** - https://hostadvice.com/how-to/how-to-enable-apache-mod_rewrite-on-an-ubuntu-18-04-vps-or-dedicated-server/
