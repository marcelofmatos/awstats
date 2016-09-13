# Awstats and postfix / zimbra

This is a simple way to analysis the postfix / zimbra log in a full graphic web page.


## Config

[Install](http://get.docker.com) docker in your mail server.


Edit file awstats.linoxide.conf and change `SiteDomain`

```
SiteDomain="example.com"
```

## Run with your own config

If your log save in path: /var/log/mail.log, and you can mount this file to the awstats server for analysis use. 

```
docker run -d --name awstats --hostname ServerName \
  -v /var/log/mail.log:/var/log/mail.log \
  -v /path/to/your.conf:/usr/lib/cgi-bin/awstats/awstats.linoxide.conf && \
  -p 8080:80 marcelofmatos/awstats_postfix
```
In this command, you will also run your server into host port 8080.

## Browse

```
http://your-awstats-ip-addr:8080/cgi-bin/awstats/awstats.pl?config=linoxide
```

Thanks to [linkerlab](https://github.com/linkerlab)


