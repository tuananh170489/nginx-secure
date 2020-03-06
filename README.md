# How to configure nginx with more secure
## Disable direct access via IP address

Edit `/etc/nginx/conf.d/default.conf` with following content:
```
server {
  listen 80 default_server;
  listen 443 ssl default_server;
  listen [::]:80 default_server;
  listen [::]:443 default_server;
  server_name "";
  ssl_certificate /path_to_cert_file;
  ssl_certificate_key /path_to_key_file;
  return 444;
}
```

## Block bad bot, bad user-agents, DDoS, etc ...
Ref: https://github.com/mitchellkrogza/nginx-ultimate-bad-bot-blocker/blob/master/MANUAL-CONFIGURATION.md
