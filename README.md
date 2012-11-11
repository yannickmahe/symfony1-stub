Symfony1 Stub
=============

The objective is to have a "get started" repo for new projects.


Included
--------

* Symfony1.4
* Bootstrap (via git submodule)
* Font Awesome (extra bootstrap icons, via submodule)
* Less.js (asset in common bundle)
* JQuery (via google CDN)

How to install
--------------

* git clone

   git clone --recursive git@github.com:yannickmahe/symfony1-stub.git

* clear cache

  php symfony cc

* setup host file

  127.0.0.1 	domain.tld

* setup apache

  ````
  NameVirtualHost domain.tld
  <VirtualHost *:80>
      ServerName domain.tld
        DocumentRoot "{{dir}}/web"
        DirectoryIndex index.php
        <Directory "{{dir}}/web">
            AllowOverride All
            Allow from All
        </Directory>


		Alias /sf "{{dir}}/lib/vendor/symfony/data/web/sf"
		<Directory {{dir}}/lib/vendor/symfony/data/web/sf">
		    AllowOverride All
		    Allow from All
		</Directory>
  </VirtualHost>
  ````

* restart apache

  sudo service apache2 restart