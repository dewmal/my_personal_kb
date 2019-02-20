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
