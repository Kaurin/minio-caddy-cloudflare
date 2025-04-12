# minio-caddy-cloudflare

Small project to launch [minio](https://github.com/minio/minio) - AWS S3 compatible file storage, with [caddy](https://github.com/mholt/caddy) as the reverse proxy.

This project has a hard requirement of a DNS zone hosted on Cloudflare.

Uses port 8443 and 8080 for user access to avoid requiring root privileges

Tested with `podman-compose`, not tested with `docker-compose`

## Bootstrap

Copy the `example.env` to `myenv.env`:
```sh
cp example.env myenv.env
```

Edit the `myenv.env` as needed

## Launch

Even though the env file spec is in docker-compose, it's defunct in podman currently [due to a bug](https://github.com/containers/podman-compose/issues/718). Because of this, we need to specify the env-file on the commandline

```sh
podman compose --env-file myenv.env up -d
```

