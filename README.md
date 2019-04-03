# yii2-advanced--.htaccess
.htaccess file for yii2-advanced for those need upload file to virtual host or server. If this is not placed correctly, it will occur some file address placed wrongly

1. At the root of the project (@app) add a ``.htaccess``
<IfModule mod_rewrite.c>
    Options +FollowSymlinks
    RewriteEngine On
</IfModule>
 
<IfModule mod_rewrite.c>    
    RewriteCond %{REQUEST_URI} ^/(admin)
    RewriteRule ^admin/assets/(.*)$ backend/web/assets/$1 [L]
    RewriteRule ^admin/css/(.*)$ backend/web/css/$1 [L]
    RewriteRule ^admin/js/(.*)$ backend/web/js/$1 [L]
    RewriteCond %{REQUEST_URI} !^/backend/web/(assets|js|css|js)/
    RewriteCond %{REQUEST_URI} ^/(admin)
    RewriteRule ^.*$ backend/web/index.php [L]
    RewriteCond %{REQUEST_URI} ^/(assets|css|js|images)
    RewriteRule ^assets/(.*)$ frontend/web/assets/$1 [L]
    RewriteRule ^css/(.*)$ frontend/web/css/$1 [L]
    RewriteRule ^js/(.*)$ frontend/web/js/$1 [L]
    RewriteRule ^images/(.*)$ frontend/web/images/$1 [L]
    RewriteRule ^(.*)$ frontend/web/$1 [L]
    RewriteCond %{REQUEST_URI} !^/(frontend|backend)/web/(assets|css|js)/
    RewriteCond %{REQUEST_URI} !index.php
    RewriteCond %{REQUEST_FILENAME} !-f [OR]
    RewriteCond %{REQUEST_FILENAME} !-d
    RewriteRule ^.*$ frontend/web/index.php
</IfModule>

note: Where ``admin`` - path to the ``@backend/web``.

2. In the @frontend/web add another ``.htaccess`` 

``frontend/.htaccess``

3. In the file @frontend/config/main.php edit the url

``frontend/config/.htaccess``
 
4. In the folder @backend/web add the file ``.htaccess`` with the content:

``backend/.htaccess``

5. In the file @backend/config/main.php add the content:

``backend/config/.htaccess``
  
  
