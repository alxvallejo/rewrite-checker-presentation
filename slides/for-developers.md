##  Who like writing rewrites?

```php
RewriteCond %{HTTP_HOST} ^(.*\.)?imprivata.(de|fr|nl)$ [NC]
RewriteCond %{REQUEST_URI} !^/(de|fr|nl)/? [NC]
RewriteCond %{REQUEST_FILENAME} !-f
RewriteCond %{REQUEST_URI} !^/node/([0-9]+)/edit/?(.*)?$ [NC]
RewriteCond %{REQUEST_URI} !^/node/([0-9]+)/translate/?(.*)?$ [NC]
RewriteCond %{REQUEST_URI} !^/(uk|intl|de|nl)/node/([0-9]+)/edit/?(.*)?$ [NC]
RewriteCond %{REQUEST_URI} !^/(uk|intl|de|nl)/node/([0-9]+)/translate/?(.*)?$ [NC]
RewriteCond %{REQUEST_URI} !^/user/?(.*)? [NC]
RewriteCond %{REQUEST_URI} !^/admin/?(.*)? [NC]
RewriteCond %{REQUEST_URI} !^/index.php [NC]
RewriteCond %{REQUEST_URI} !^/field_collection/(.*)? [NC]
RewriteRule ^(.*)$ https://www.imprivata.%2/%2%{REQUEST_URI} [R=301,L,NC]
```