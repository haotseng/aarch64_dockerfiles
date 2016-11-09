# Let's Encrypt certbot for ARM64 architecture

---

Build Source :
https://github.com/haotseng/aarch64_dockerfiles

---

## How to build image :

    docker build -t ebspace/aarch64-letcrypt-certbot:latest .

---

## How to Use this Images

Example to get cerificates (Use the staging server to obtain test (invalid) certs) :
 
    docker run -it --rm -p 443:443 -p 80:80 --name certbot      \
           -v "$(pwd)/letsencrypt_conf:/etc/letsencrypt"        \
           -v "$(pwd)/letsencrypt_work:/var/lib/letsencrypt"    \
           -v "$(pwd)/letsencrypt_logs:/var/log/letsencrypt"    \
           ebspace/aarch64-letcrypt-certbot:latest              \
           certonly --test-cert --no-self-upgrade --standalone  \
           -d www.example.com -d example.com

Example to renew cerificates (Use the staging server to obtain test (invalid) certs):

    docker run -it --rm -p 443:443 -p 80:80 --name certbot    \
           -v "$(pwd)/letsencrypt_conf:/etc/letsencrypt"      \
           -v "$(pwd)/letsencrypt_work:/var/lib/letsencrypt"  \
           -v "$(pwd)/letsencrypt_logs:/var/log/letsencrypt"  \
           ebspace/aarch64-letcrypt-certbot:latest            \
           renew --test-cert  --no-self-upgrade --standalone  \
           -d www.example.com -d example.com

For more certbot-auto arguments , please refer https://certbot.eff.org/docs/


           
           


