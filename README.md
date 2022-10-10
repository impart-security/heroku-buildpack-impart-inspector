
Heroku buildpack: impart-inspector
=======================

Usage
-----

Add buildpack
```
heroku create --buildpack https://github.com/impart-security/heroku-buildpack-impart-inspector
```

Create impart-inspector access token in the console and set config value
```
heroku config:set INSPECTOR_API_ACCESS_TOKEN=<access_token_value>
```

Resgister a new binding in the console
```
Hostname: <app>.herokuapp.com
Port: 80
Upstream Origin: http://127.0.0.1:8080
```


Run command:
```
bin/inspector --http_listen_addr=:$PORT --http_listener_disable_tls &
```





