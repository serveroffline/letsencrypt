# letsencrypt
Tiny scripts for Let's Encrypt to automate deploy and renewal

Just make a cron-job as a user with enough rights to deploy and run let's encrypt plus the ability to reload the NGINX config (or whichever you want to use, I simply used NGINX in this one but it can be any...)

0 0 * * * /opt/letsencrypt/cron/automated_renewal
