# yii2-advanced--.htaccess
.htaccess file for yii2-advanced for those need upload file to virtual host or server. If this is not placed correctly, it will occur some file address placed wrongly

1. At the root of the project (@app) add a ``.htaccess``

``.htaccess``

note: Where ``admin`` - path to the ``@backend/web``.

2. In the @frontend/web add another ``.htaccess`` 

``frontend/.htaccess``

3. In the file @frontend/config/main.php edit the url

``frontend/config/.htaccess``
 
4. In the folder @backend/web add the file ``.htaccess`` with the content:

``backend/.htaccess``

5. In the file @backend/config/main.php add the content:

``backend/config/.htaccess``
  
  references/original link: https://devreadwrite.com/posts/htaccess-for-yii-2-advanced
  
