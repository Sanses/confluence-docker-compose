#SSL Certification Restore

[root@wiki-vm confluence-docker-compose]# docker-compose down

[root@wiki-vm confluence-docker-compose]# certbot-auto certonly --cert-name wiki.iisanse.com -d wiki.iisanse.com

[root@wiki-vm confluence-docker-compose]# cp /etc/letsencrypt/live/wikisanse.crt/fullchain.pem ~/workspace/confluence-docker-compose/ssl
[root@wiki-vm confluence-docker-compose]# cp /etc/letsencrypt/live/wikisanse.crt/privkey.pem ~/workspace/confluence-docker-compose/ssl

[root@wiki-vm confluence-docker-compose]# docker-compose up -d --build
