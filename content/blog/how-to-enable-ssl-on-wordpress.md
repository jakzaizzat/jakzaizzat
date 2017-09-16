---
title: "How to Enable Ssl on Wordpress"
date: 2017-08-09T13:01:11+08:00
draft: false
---

Have an SSL on your website will increase SEO your site on the Google, Increase trustworthy visitors and make user know that you cared the website. I just enable the SSL on this website; this is how I do it. There are manual setup or using plugins. Choose which one was suitable for you. I will teach the harder first (not so much), and then we go to the simple step.  It required around 5 minutes.


## Manual Setup


First of all, login to the **WordPress** dashboard and go to the **Settings  &#x2192; General** and changed the existing URL into new URL with https:// at the front. Don’t forget to save the settings.

![WordPress URL](/image/20170809/wordpress url.png)

Open the **.htaccess** file and add the code below. The **.htaccess** file can’t be found in WordPress, you may find it through hosting either using Cpanel, Filezilla or terminal.
```
<IfModule mod_rewrite.c>
RewriteEngine On
RewriteCond %{SERVER_PORT} 80
RewriteRule ^(.*)$ https://www.yoursite.com/$1 [R,L]
</IfModule>
```

If you’re using **Nginx** server, please add this code below. Replace yoursite.com with your URL

```
server {
listen 80;
server_name yoursite.com www.yoursite.com;
return 301 https://yoursite.com$request_uri;
}
```

If you are using Cpanel likes me, you may see it on the current WordPress installation folder **(/public_html/)** and if you didn’t find it, the file is hidden. You may show the hidden file by clicking the setting button on top right and tick the show hidden files option.

![Cpanel Settings](/image/20170809/cpanel option.png)
![Cpanel Preferences](/image/20170809/cpanel preferences.png)
Eureka, now the file has appeared and you able to edit the file now.

![.HTCACCESS](/image/20170809/cpanel file.png)

Now, your WordPress has enabled SSL. Congratulations.




## Plugins Setup

This step suitable for someone who didn't want to work with technical stuff. If you have the intention to minimize the plugin's usage on the WordPress, try to use manual setup first.

First, log in to WordPress dashboard and go to the **Plugins &#x2192; Add New**. Search for SSL in the search bar at the top.

![WordPress Plugins Directory](/image/20170809/wordpress plugin.png)

Choose Really Simple SSL and click install Now. Activate the plugins, and you’re done. It required to login once again to fully support the SSL.

![Really Simple SSL Plugins](/image/20170809/really simple ssl plugins.png)
