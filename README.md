# Getting Started

## Configuration

Create a file called `.env` with the following content:

```
GUACPASS=[password]
HOSTNAME=[hostname]
EMAIL=[your@email]
```

## Certificates

If you are ok with self-signed certs, you don't need to do anything. If you want root-signed certs from Let's Encrypt, then edit `docker-compose.yml` as follows:
- Uncomment the `LETSENCRYPT` variables
- Delete the `SELF_SIGNED` environment variable
- Make sure your e-mail address and hostname are correct in your `.env` file