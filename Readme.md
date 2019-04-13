# Heimdall config
This repo contains an `nginx` config based on the one from Heimdall, which also proxies a Home Assistant `emulated_hue` as Sleep Cycle requires `emulated_hue` to be on port 80.
Since the Home Assistant container runs with `--net=host` and this is proxying it, we need it here too.

```bash
docker run -d \
  -e PGID=1000 -e PUID=1000 -e TZ=Pacific/Auckland \
  --net=host \
  -v /home/matthew/docker/heimdall:/config \
  --name=heimdall --restart=unless-stopped \
  linuxserver/heimdall
```
