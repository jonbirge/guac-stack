# Getting Started

## EULA

Note that this compose stack pulls two containers from Glyptodon. You will need to [create an account with Glyptodon](https://glyp.to) so that you can legally use their containers. For individuals employing their containers for personal use, they generously offer a license for free. That said, I know this isn't optimal; if somebody were willing to find open source alternatives to the Glyptodon containers, I would be grateful for that pull request!

## Configuration

Rename the file called `config.env` to `.env` and edit the following content to match your system:

```
GUACPASS=[anypassword]
HOSTNAME=[hostname]
EMAIL=[email]
```

## Certificates

If you are ok with self-signed certs, you don't need to do anything. If you want root-signed certs from Let's Encrypt, then edit `docker-compose.yml` as follows:
- Uncomment the `LETSENCRYPT` variables
- Delete the `SELF_SIGNED` environment variable
- Make sure your e-mail address and hostname are correct in your `.env` file

## Running

Once you've configured the environment variables in the `.env` file, you should just be able to run

```
$ docker-compose up -d
```
