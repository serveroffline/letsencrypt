# letsencrypt
Tiny scripts for Let's Encrypt to automate deploy and renewal

Just make a cron-job as a user with enough rights to deploy and run let's encrypt plus the ability to reload the NGINX config (or whichever you want to use, I simply used NGINX in this one but it can be any...)

0 0 * * * /opt/letsencrypt/cron/automated_renewal

# Default installation parameters
$ git clone https://github.com/letsencrypt/letsencrypt
$ mv letsencrypt /opt/letsencrypt
$ mkdir -p /var/www/letsencrypt/html

# /etc/letsencrypt/cli.ini
rsa-key-size = 4096
email = example@example.net
authenticator = webroot
webroot-path = /var/www/letsencrypt/html
text = True
agree-tos = True
renew-by-default = True

# /etc/nginx/conf.d/letsencrypt.conf
location /.well-known/acme-challenge {
    default_type  "text/plain";
    root          /var/www/letsencrypt/html;
}
