
Heroku buildpack: impart-inspector
=======================

Usage
-----

Add buildpack
```
heroku create --buildpack https://github.com/impart-security/heroku-buildpack-impart-inspector
```

Login to https://console.impartsecurity.net/. Under manage secretion click integrations => impart inspector and create an access token with scopes:
```
read:inspector_settings
write:inspector_metrics
```

Set INSPECTOR_API_ACCESS_TOKEN env variable:
```
heroku config:set INSPECTOR_API_ACCESS_TOKEN=<access_token_value>
```

Register a new binding in the console.
Bingings=>New binding:
enter binding name and select specification or create a new specification.
The heroku application must be listening on local interface for example if it's listening on port 8080 upstream origin must be http://127.0.0.1:8080.

Example configuration values:
```
Hostname: <app>.herokuapp.com
Port: 80
Base Path: /
Upstream Origin: http://127.0.0.1:8080
```

If binding is not resigered the inspector will respond with 502 Bad Gateway error.

Run command:
```
bin/inspector --http_listen_addr=:$PORT --http_listener_disable_tls &
```





