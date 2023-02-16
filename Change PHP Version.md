```
## Add Ondřej Surý's php ppa repository

sudo add-apt-repository ppa:ondrej/php
sudo apt-get update


## Install apache

sudo apt-get install apache2


## Install php

sudo apt-get install php7.4 php7.4-dev php7.4-curl php7.4-mbstring php7.4-bcmath php-pear php7.4-zip php7.4-xml php7.4-gd php7.4-imagick


# Set PHP 7.4 as default PHP version

sudo update-alternatives --set php /usr/bin/php7.4
sudo update-alternatives --set phar /usr/bin/phar7.4
sudo update-alternatives --set phar.phar /usr/bin/phar.phar7.4
sudo update-alternatives --set phpize /usr/bin/phpize7.4
sudo update-alternatives --set php-config /usr/bin/php-config7.4

```
