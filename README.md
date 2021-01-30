# mastodon-traefikv2-docker-compose
Mastodon Instance based on Docker Compose. Requires a Traefik Load Balancer

## Demo

Visit https://www.r-kara.de for a demo of my own Mastodon Instance

## Install

Download my docker-compose.yml and fill in the variables to your needs

In the same directory run:

```touch .env.production```

On linux machines: ```sudo chown 991:991 .env.production```

```docker-compose run --rm -v $(pwd)/.env.production:/opt/mastodon/.env.production web bundle exec rake mastodon:setup```

This will guide you through some steps setting up things like Users, Secrets, etc. don’t worry.

```docker-compose up -d```

That should be it. You now have an instance of Mastodon running behind a traefik reverse-proxy handling HTTPS redirection, TLS termination and automagic setup and renewal of Let’s Encrypt certificates. Persistence data from the containers is stored in folders located in the same directory as your docker-compose.yml.
