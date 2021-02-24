# full nginx config with cloudflare ssl (full)

* generate cert.pem and key.pem in cloudflare (origin server tab)
* place the key to /docker-webstack/etc/ssl/certs && private
* use this nginx config
* restart web server

debug

1 - if got this error 

```
[emerg] 1#1: cannot load certificate key "/etc/ssl/private/key.pem": BIO_new_file() failed (SSL: error:02001002:system library:fopen:No such file or directory:fopen('/etc/ssl/private/key.pem','r') error:2006D080:BIO routines:BIO_new_file:no such file

```

change permission for the certificate

```
sudo chown -R root:root ssl
sudo chmod -R 600 ssl

```

