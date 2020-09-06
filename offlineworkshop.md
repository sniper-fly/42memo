/var/www/html/　にwordpressやphpmyadminを展開する  
/var/www/html/wordpress/wp-config.php をwp-config-sample.phpをcp  
/etc/nginx/sites-available/defaultに設定が書き込まれてる  
# Add index.php to the list if you are using PHPの下に追記  
index.php

location ~ \.php$ {
                include snippets/fastcgi-php.conf;
        #
        #       # With php-fpm (or other unix sockets):
                fastcgi_pass unix:/run/php/php7.3-fpm.sock;
        #       # With php-cgi (or other tcp sockets):
        #       fastcgi_pass 127.0.0.1:9000;
                fastcgi_param SCRIPT_FILENAME $document_root$fastcgi_script_name;
                include fastcgi_params;
        }  
参照  
https://qiita.com/MiyaseTakurou/items/923c28f7ac60b2ce761a  

/** The name of the database for WordPress */  
define( 'DB_NAME', 'wordpress' );

/** MySQL database username */  
define( 'DB_USER', 'rnakai@localhost' );

/** MySQL database password */  
define( 'DB_PASSWORD', 'passwd' );

/** MySQL hostname */  
define( 'DB_HOST', 'localhost' );

/** Database Charset to use in creating database tables. */  
define( 'DB_CHARSET', 'utf8' );

/** The Database Collate type. Don't change this if in doubt. */  
define( 'DB_COLLATE', '' );


service nginx start  
service nginx restart で再起動（設定の再読み込みなどができる）

service mysql start  
service php7.3-fpm  

phpmyadminでは自分で作ったuser名とpasswordを使う  
今回はrnakai@localhost & passwd  

docker commit でimageの更新ができる  

mysql -u [user name] -p  
-uはユーザー名を指定、-pでpasswordをこれから入力するよ　という意味  

sql実行中コマンド  
use wordpress  
use [table name]  

MariaDB [(none)]> create user 'rnakai'@'localhost' identified by 'password';  

create user '[user name]'@'[ip]' identified by '[password]'  
create database wordpress;  
wordpressというテーブルを作る  

sql文  
select user, host from user;

sql設定
grant all on wordpress.* to '[user name]';  
flush privileges;  
