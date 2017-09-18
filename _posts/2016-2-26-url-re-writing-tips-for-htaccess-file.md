---
layout: post
title: 'URL re-writing: Tips for .htaccess file'
comments: true
author: Lucas Callado
categories:
  - Web Development
---
.htaccess

**\*\\*\* Rewrite folder name to a filename \*\*\***

Admin url is folder/cms-admin/index.php and access should be folder/admin

<pre>RewriteRule ^admin cms-admin/index.php [R]
</pre>

**\*\\*\* All requests to page.html will be sent to page.php \*\*\***

This will rewrite any filename with .html to .php

<pre>Options +FollowSymlinks
RewriteEngine on
RewriteRule ^(.*)\.html$ $1.php [NC]
</pre>

[NC] means &#8220;No Case Sensitive&#8221;;

**\*\\*\* All files of .html to .php \*\*\***

<pre>RewriteRule ^(.+)\.html$ http://site.com/$1.php
</pre>

**\*\\*\* Rewrite www to non www url \*\*\***

<pre>RewriteCond %{HTTP_HOST} ^www.site.com [NC]
RewriteRule ^(.*)$ http://site.com/$1 [L,R=301]

RewriteCond %{HTTP_HOST} ^www.site.com [NC]
RewriteRule ^(.*)$ http://site.com/folder/$1 [L,R=301]
</pre>

**\*\\*\* Rewrite non www to www \*\*\***

<pre>RewriteCond %{HTTP_HOST} ^site\.com
RewriteRule (.*) http://www.site.com/$1 [R=301,L]
</pre>

**\*\\*\* Rewrite non www to www with https \*\*\***

All non www url will be re-written to www with prefix https

<pre>RewriteCond %{SERVER_PORT} 80
RewriteRule ^(.*)$ https://www.site.com/$1 [R,L]

RewriteCond %{HTTP_HOST} ^site\.com
RewriteRule (.*) https://www.site.com/$1 [R=301,L]
</pre>

**\*\\*\* Redirect http to https on one page only \*\*\***

<pre>RewriteCond %{SERVER_PORT} !^443$
RewriteRule ^contact/?$ https://secure.example.com/contact/ [R=301,L]
</pre>

<pre>RewriteEngine On
RewriteCond %{SERVER_PORT} 80
RewriteCond %{REQUEST_URI} folderName
RewriteRule ^(.*)$ https://www.site.com/folderName/$1 [R,L]
</pre>

**\*\\*\* Rewrite file links \*\*\***

<pre>Options +FollowSymlinks
RewriteEngine on
RewriteRule ^files/([^/]+)/([^/]+).zip /download.php?section=$1&file=$2 [NC]
</pre>

Final result:

site.com/files/foo.zip

**\*\\*\* Rewrite http to https for only one folder \*\*\***

<pre>RewriteEngine on
DirectoryIndex index.php index.html
RewriteCond %{SERVER_PORT} 80
RewriteRule ^(.*)$ https://www.site.com/test/$1 [R,L]
</pre>
