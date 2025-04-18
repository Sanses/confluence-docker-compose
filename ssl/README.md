# Certbot-auto Install
[root@wiki-vm]# snap install --classic certbot

[root@wiki-vm]# ln -s /snap/bin/certbot /usr/bin/certbot


# SSL Certification Create

[root@wiki-vm confluence-docker-compose]# docker-compose down

[root@wiki-vm confluence-docker-compose]# certbot certonly --standalone -d wiki.sansae.net

[root@wiki-vm confluence-docker-compose]# cp /etc/letsencrypt/live/wiki.sansae.net/fullchain.pem ssl

[root@wiki-vm confluence-docker-compose]# cp /etc/letsencrypt/live/wiki.sansae.net/privkey.pem ssl

[root@wiki-vm confluence-docker-compose]# docker-compose up -d
