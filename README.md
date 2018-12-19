# Traefik reverse proxy

Don't forget to :

0. Have your subdomains setup.

1. Create the acme file
```bash
touch acme.json
chmod 600 acme.json
```

2. Create user(s) credentials
```bash
sudo apt-get install apache2-utils
htpasswd -nb admin secure_password
```

3. Set user(s) credentials and email address in `traefik.toml`
```
cp traefik.default.toml traefik.toml
nano traefik.toml
# set user credentials to the hash from htpasswd
# set email to something
```

4. Set the front-end rule for the Traefik dashboard in `docker-compose.yml`.
```
cp docker-compose.default.yml docker-compose.yml 
nano docker-compose.yml
# set monitor subdomain in front-end rule
```

5. Create a docker network called proxy.
```bash
sudo docker network create proxy
```
