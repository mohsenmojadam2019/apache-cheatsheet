# Cors
## Set cors headers
```
Header always set Access-Control-Allow-Origin "*"
Header always set Access-Control-Allow-Methods  "*"
Header always set Access-Control-Allow-Headers "Content-Type, x-requested-with, Authorization, Accept"
```
## Add cors headers (May result duplicate headers)
```
Header add Access-Control-Allow-Origin "*"
Header add Access-Control-Allow-Methods  "*"
Header add Access-Control-Allow-Headers "Content-Type, x-requested-with, Authorization, Accept"
```
# Proxy pass
## Proxy pass http and websocket
```
ProxyPass "/"  "http://localhost:3000/"
#ProxyPassReverse "/"  "http://localhost:3000/"
RewriteCond %{HTTP:Upgrade} websocket [NC]
RewriteCond %{HTTP:Connection} upgrade [NC]
RewriteRule ^/?(.*) "ws://localhost:3000/$1" [P,L]
```

# Other
## Set status code
```
RewriteRule ^ - [R=410,L]
```
## Unset Header
```
Header unset Access-Control-Allow-Origin
```
