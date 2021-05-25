# lando-wordpress
Lando config for WordPress local development.

## Contents
- Latest version of WordPress
- Apache 2.4 (version adjustable in .lando.yml)
- PHP 7.2 (version adjustable in .lando.yml)
- MySQL 5.7 (version adjustable in .lando.yml)
- PHPMyAdmin
- Mailhog

## Installation
[Install Lando](https://docs.lando.dev/basics/installation.html) and run the commands:
```
git clone https://github.com/pavlowp/lando-wordpress.git
cd lando-wordpress
lando start
```

## URLs
All URLs have both http and https versions.
- `wordpress.lndo.site` - WordPress
- `db.wordpress.lndo.site` - PHPMyAdmin
- `mail.wordpress.lndo.site` - Mailhog

## Trusting the CA
### MacOS
```
# Add the Lando CA
sudo security add-trusted-cert -d -r trustRoot -k /Library/Keychains/System.keychain ~/.lando/certs/lndo.site.pem

# Remove Lando CA
sudo security delete-certificate -c "Lando Local CA"
```
### Windows
```
# Add the Lando CA
certutil -addstore -f "ROOT" C:\Users\ME\.lando\certs\lndo.site.pem

# Remove Lando CA
certutil -delstore "ROOT" serial-number-hex
```
More info about Land CA [here](https://docs.lando.dev/config/security.html#trusting-the-ca).


## Other Commands
- `lando stop` - Stop Lando instance (DB and files won't be deleted)
- `lando destroy` - Destroy Lando instance (DB and files ***will*** be deleted)
- `lando rebuild` - Rebuild the instance if the config was changed (DB and files won't be deleted)
- `lando poweroff` - Stop all Lando instances including the proxy container

## Performance
Lando setup may have some performance issues.
More info about Lando performance [here](https://docs.lando.dev/config/performance.html#configuration).
