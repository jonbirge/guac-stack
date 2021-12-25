# Getting Started

## EULA

Note that this compose stack pulls two containers from Glyptodon. You will need to [create an account with Glyptodon](https://glyp.to) so that you can legally use their containers. For individuals employing their containers for personal use, they generously offer a license for free. That said, I know this isn't optimal; if somebody were willing to find open source alternatives to the Glyptodon containers, I would be grateful for that pull request!

## Configuration

Rename the file called `config.env` to `.env` and edit the following content to match your system:

```
GUACPASS=[anypassword]
HOSTNAME=[hostname]
EMAIL=[email]
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

Connect at `https://hostname/guacamole/`
