# A Portainer client to watch other Agent

## Create a 1Gb volume for portainer

```bash
fly volumes create hophamlam_portainer_vol --region sin --size 1
```

Paste the volume name to [mount] part in `fly.toml`. Example:

```toml
[mounts]
  destination = "/app/data"
  source = "hophamlam_portainer_vol"
```

```bash
flyctl deploy
```

## Add custom domain

Change into your domain + Use CNAME to point your domain to auto-generated fly.clio app url

```bash
flyctl certs create status.mydomain.com
```

Do the same with `www.status.mydomain.com`
