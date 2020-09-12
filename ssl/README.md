# Certbot-auto Install
[root@wiki-vm]# wget https://dl.eff.org/certbot-auto

[root@wiki-vm]# mv certbot-auto /usr/local/bin/certbot-auto

[root@wiki-vm]# chown root /usr/local/bin/certbot-auto

[root@wiki-vm]# chmod 0755 /usr/local/bin/certbot-auto


# SSL Certification Restore

[root@wiki-vm confluence-docker-compose]# docker-compose down

[root@wiki-vm confluence-docker-compose]# certbot-auto renew --force-renewal --cert-name wikisanse.crt

[root@wiki-vm confluence-docker-compose]# cp /etc/letsencrypt/live/wikisanse.crt/fullchain.pem /root/workspace/confluence-docker-compose/ssl

[root@wiki-vm confluence-docker-compose]# cp /etc/letsencrypt/live/wikisanse.crt/privkey.pem /root/workspace/confluence-docker-compose/ssl

[root@wiki-vm confluence-docker-compose]# docker-compose up -d --build

# INFO
[root@wiki-vm confluence-docker-compose]# docker-compose down
Stopping nginx      ... done
Stopping confluence ... done
Stopping postgres   ... done
Removing nginx      ... done
Removing confluence ... done
Removing postgres   ... done
Removing network confluence-docker-compose_default
[root@wiki-vm confluence-docker-compose]#
[root@wiki-vm confluence-docker-compose]#
[root@wiki-vm confluence-docker-compose]#
[root@wiki-vm confluence-docker-compose]# certbot-auto renew --force-renewal --cert-name wikisanse.crt
Saving debug log to /var/log/letsencrypt/letsencrypt.log

- - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - -
Processing /etc/letsencrypt/renewal/wikisanse.crt.conf
- - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - -
Plugins selected: Authenticator standalone, Installer None
Renewing an existing certificate
Performing the following challenges:
http-01 challenge for wiki.iisanse.com
Waiting for verification...
Cleaning up challenges

- - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - -
new certificate deployed without reload, fullchain is
/etc/letsencrypt/live/wikisanse.crt/fullchain.pem
- - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - -

- - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - -

Congratulations, all renewals succeeded. The following certs have been renewed:
  /etc/letsencrypt/live/wikisanse.crt/fullchain.pem (success)
- - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - -
[root@wiki-vm confluence-docker-compose]#
