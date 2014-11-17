This is munin plugin for count of Nginx access.log.


# How to setup

```
# cd /usr/share/munin/plugins/
# wget --no-check-certificate https://raw.githubusercontent.com/takeshiyako2/munin-nginx_access_log/master/nginx_access_log
# chmod +x nginx_access_log
# ln -s /usr/share/munin/plugins/nginx_access_log /etc/munin/plugins/nginx_access_log
# munin-run nginx_access_log
nginx_access_log.value 5413
# service munin-node restart
```


# AUTHOR

Contributed by Takeshi Yako
https://github.com/takeshiyako2

# LICENSE

MIT

