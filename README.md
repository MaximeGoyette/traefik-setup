# Traefik reverse proxy

Don't forget to :

1. Create the acme file
```bash
touch acme.json
chmod 600 acme.json
```

2. Create an admin password
```bash
sudo apt-get install apache2-utils
htpasswd -nb admin secure_password
```

3. Set password and email in `traefik.toml`

4. Set the front-end rule for the Traefik dashboard in `docker-compose.yml`.
