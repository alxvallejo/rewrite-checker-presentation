## Who likes writing rewrites?

```php
# When TLD is .de, .fr, or .nl
# And request URI does not begin with /de/, /fr/, /nl/
# And not an admin page
# And no PHP session cookie
# Redirect to https://www.imprivata.[TLD]/[TLD]/[REQUEST_URI]
RewriteCond %{HTTP_HOST} ^(.*\.)?imprivata.(de|fr|nl)$ [NC]
RewriteCond %{REQUEST_URI} !^/(de|fr|nl)/? [NC]
RewriteCond %{REQUEST_FILENAME} !-f
RewriteCond %{REQUEST_URI} !^/node/([0-9]+)/edit/?(.*)?$ [NC]
RewriteCond %{REQUEST_URI} !^/node/([0-9]+)/translate/?(.*)?$ [NC]
RewriteCond %{REQUEST_URI} !^/(uk|intl|de|nl|fr)/node/([0-9]+)/edit/?(.*)?$ [NC]
RewriteCond %{REQUEST_URI} !^/(uk|intl|de|nl|fr)/node/([0-9]+)/translate/?(.*)?$ [NC]
RewriteCond %{REQUEST_URI} !^/user/?(.*)? [NC]
RewriteCond %{REQUEST_URI} !^/admin/?(.*)? [NC]
RewriteCond %{REQUEST_URI} !^/index.php [NC]
RewriteCond %{REQUEST_URI} !^/field_collection/(.*)? [NC]
RewriteCond %{HTTP_COOKIE} !SSESS [NC]
RewriteRule ^(.*)$ https://www.imprivata.%2/%2%{REQUEST_URI} [R=301,L,NC]
```