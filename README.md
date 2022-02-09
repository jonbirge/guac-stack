# Getting Started

## About

This repo is just a docker-compose file and associated environment settings file that allows you to instantly stand up an Apache Guacamole stack using Docker. If you don't know what Guacamole is, you probably don't care about this, but if you do you'll know that initially configuring it and setting up the bare database takes a while. This takes advantage of Docker and some really nice containers from Glyptodon to automate the setup of the various services, the creation of the initial SQL database, as well as the configuration of an HTTPS reverse proxy with externally-signed certificates.

## Glyptodon EULA

Note that this compose stack pulls two container images from Glyptodon. You will need to [create an account with Glyptodon](https://glyp.to) so that you can legally use their software. For individuals employing the containers for personal use, they generously offer a license for free.

## Configuration

Rename the file called `config.env` to `.env` and edit the content to match your system:

```
GUACPASS=[anypassword]
HOSTNAME=[hostname]
EMAIL=[email-for-lets-encrypt]
SELFSIGN=["Y"|"N"]
```

## Certificates

If you are ok with self-signed certs, you don't need to do anything. If you want root-signed certs from Let's Encrypt, then do the following in `.env`:
- Set the `SELFSIGN` variable to "N".
- Make sure `HOSTNAME` is your full public server domain name. 
- Set your e-mail to something you're willing to give to Let's Encrypt.

## Running

Once you've configured the environment variables in the `.env` file, you should just be able to run

```
$ docker-compose up -d
```

Connect at `https://hostname/guacamole/`.

## Requests

I know using closed-source software for this isn't optimal; if somebody were able to make or find open source alternatives to the Glyptodon containers, I would be grateful for that pull request! For other minor things, check out the Issues in this repo.
