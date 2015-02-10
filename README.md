This is munin plugin for count of Nginx access.log.


![munin-nginx_access_log example](https://raw.githubusercontent.com/takeshiyako2/munin-nginx_access_log/master/images/example.png "munin-nginx_access_log example")

# How to setup


Change log file permission.
```
# chmod 644 /var/log/nginx/*.log
```

Add "create 644 nginx adm" to nginx logrotate.d file.
```
# cat /etc/logrotate.d/nginx 
/var/log/nginx/*.log {
        daily
        missingok
        rotate 52
        compress
        delaycompress
        notifempty
        create 644 nginx adm
        sharedscripts
        postrotate
                [ -f /var/run/nginx.pid ] && kill -USR1 `cat /var/run/nginx.pid`
        endscript
}
```

Set plugin.
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

