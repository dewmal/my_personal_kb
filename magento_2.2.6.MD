## Static content deploy issue

It got a solution, which may not be 100% right.

    change developer mode to default
    Also,Manually by clearing the pub/static and var/view_preprocessed directories and subdirectories. except for pub/static/.htaccess
    Then run php  bin/magento setup:static-content:deploy and it successfully generate static files.
   change default mode to default
    bin/magento setup:static-content:deploy and it successfully generate static files again.

### If not update theme after upload

```
rm -R pub/static/frontend/*
rm -R var/view_preprocessed/pub/static/frontend/*
php  bin/magento setup:static-content:deploy -f

```
 ### if not update default.xml ( layout )
 Check thyeme type in mysql table.
 if should be 0, 1 mean virtual
 ```
 UPDATE rad_theme SET type=0;
 ```
 
 ### There has been an error processing your request, Error log record number
 
```
Go to magento/var/report
```
### Base Url Change Magento2.1



    Update baseurl in core_config_data:

    UPDATE core_config_data
    SET value = 'http://www.domain2.net/' 
    WHERE path IN ('web/secure/base_url', 'web/unsecure/base_url');

    Replace design/head/includes/

    UPDATE core_config_data 
    SET value = REPLACE(value, 'http://www.domain1.net/', 'http://www.domain2.net/') 
    WHERE path = 'design/head/includes';

Then changed Store Url

 php bin/magento setup:store-config:set --base-url="http://www.domain2.net/"

 php bin/magento setup:store-config:set --base-url-secure="https://www.domain2.net/"

Finally cleared the cache:

php bin/magento cache:flush



First update both the web/unsecure/base_url and web/secure/base_url URLs in core_config_data to http://www.domain2.net/ in your database. ( you can use the above query).

Then clear the cache by below command.

sudo rm -rf var/cache var/generation var/page_cache

Ensure you have updated your virtual host settings according to the new URL.

Once you set the applied the virtual host changes, restart the apache server.

Now browse with the new URL.


