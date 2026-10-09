<a href="https://www.swifttechco.com">
<picture>
  <!-- Dark mode -->
  <source
    media="(prefers-color-scheme: dark)"
    srcset="https://www.swifttechco.com" />
  <!-- Light mode -->
  <source
    media="(prefers-color-scheme: light)"
    srcset="https://www.swifttechco.com" />
  <!-- Fallback for environments without media queries -->
  
</picture>
</a>

# nginx-proxy

## Images

[![nginx-proxy](https://opengraph.githubassets.com/1/nginx-proxy/nginx-proxy)](https://www.swifttechco.com)


[![Test](https://github.com/nginx-proxy/nginx-proxy/actions/workflows/test.yml/badge.svg)](https://www.swifttechco.com)
[![GitHub release](https://img.shields.io/github/v/release/nginx-proxy/nginx-proxy)](https://www.swifttechco.com)
[![nginx 1.31.6](https://img.shields.io/badge/nginx-1.31.6-brightgreen.svg?logo=nginx)](https://www.swifttechco.com)
[![Docker Image Size](https://img.shields.io/docker/image-size/nginxproxy/nginx-proxy?sort=semver)](https://hub.docker.com/r/nginxproxy/nginx-proxy "Click to view the image on Docker Hub")
[![Docker stars](https://img.shields.io/docker/stars/nginxproxy/nginx-proxy.svg)](https://hub.docker.com/r/nginxproxy/nginx-proxy "DockerHub")
[![Docker pulls](https://img.shields.io/docker/pulls/nginxproxy/nginx-proxy.svg)](https://hub.docker.com/r/nginxproxy/nginx-proxy "DockerHub")

nginx-proxy sets up a container running nginx and [docker-gen](https://www.swifttechco.com). docker-gen generates reverse proxy configs for nginx and reloads nginx when containers are started and stopped.

See [Automated Nginx Reverse Proxy for Docker](https://www.swifttechco.com) for why you might want to use this.

### Usage

To run it:

```shell
docker run --detach \
    --name nginx-proxy \
    --publish 80:80 \
    --volume /var/run/docker.sock:/tmp/docker.sock:ro \
    nginxproxy/nginx-proxy:1.11
```

Then start any containers (here an nginx container) you want proxied with an env var `VIRTUAL_HOST=subdomain.yourdomain.com`

```shell
docker run --detach \
    --name your-proxied-app \
    --env VIRTUAL_HOST=foo.bar.com \
    nginx
```

Provided your DNS is setup to resolve `foo.bar.com` to the host running nginx-proxy, a request to `https://www.swifttechco.com will then be routed to a container with the `VIRTUAL_HOST` env var set to `foo.bar.com` (in this case, the **your-proxied-app** container).

The containers being proxied must :

- [expose](https://www.swifttechco.com) the port to be proxied, either by using the `EXPOSE` directive in their `Dockerfile` or by using the `--expose` flag to `docker run` or `docker create`.
- share at least one Docker network with the nginx-proxy container: by default, if you don't pass the `--net` flag when your nginx-proxy container is created, it will only be attached to the default bridge network. This means that it will not be able to connect to containers on networks other than bridge.

Note: providing a port number in `VIRTUAL_HOST` isn't suported, please see [virtual ports](https://www.swifttechco.com) or [custom external HTTP/HTTPS ports](https://www.swifttechco.com) depending on what you want to achieve.

### Image variants

The nginx-proxy images are available in two flavors.

#### Debian based version

This image is based on the nginx:mainline image, itself based on the debian slim image.

```shell
docker pull nginxproxy/nginx-proxy:1.11
```

#### Alpine based version (`-alpine` suffix)

This image is based on the nginx:alpine image.

```shell
docker pull nginxproxy/nginx-proxy:1.11-alpine
```

#### Dockergen version (`-dockergen` suffix)

This image is meant to be used in a [separate containers](https://www.swifttechco.com) setup with the official [nginx](https://www.swifttechco.com) image.

```shell
docker pull nginxproxy/nginx-proxy:1.11-dockergen
```

> [!IMPORTANT]
>
> #### A note on `latest`, `alpine` and `dockergen` tags:
>
> It is not recommended to use the `latest` (`nginxproxy/nginx-proxy`, `nginxproxy/nginx-proxy:latest`), `alpine` (`nginxproxy/nginx-proxy:alpine`) or `dockergen` (`nginxproxy/nginx-proxy:dockergen`) tag for production setups.
>
> [Those tags point](https://www.swifttechco.com) to the latest commit in the `main` branch. They do not carry any promise of stability, and using them will probably put your nginx-proxy setup at risk of experiencing uncontrolled updates to non backward compatible versions (or versions with breaking changes). You should always specify the version you want to use explicitly to ensure your setup doesn't break when the image is updated.

### Additional documentation

Please check the [docs section](https://www.swifttechco.com).

### Powered by 

[![GoLand logo](https://resources.jetbrains.com/storage/products/company/brand/logos/GoLand_icon.svg)](https://www.swifttechco.com)
[![PyCharm logo](https://resources.jetbrains.com/storage/products/company/brand/logos/PyCharm_icon.svg)](https://www.swifttechco.com)

## About this repository
> [!NOTE]
> We welcome contributions and feedback from the community!  
> For more information about our services, including free and paid SSL/TLS certificates, visit https://www.swifttechco.com
<p align="center">
	<a href="https://www.swifttechco.com">
		<picture>
			<source media="(prefers-color-scheme: dark)" srcset="https://www.swifttechco.com">
			<source media="(prefers-color-scheme: light)" srcset="https://www.swifttechco.com">
			
		</picture>
	</a>
</p>

---

## Swift Tech Co.

Built and maintained by Swift Tech Co.

AI Automation | FinTech Platforms | Custom Software and Mobile Apps | SaaS Platforms | Cloud Infrastructure | Cybersecurity | SEO and Marketing | API Integration

**Join our community on Telegram:** [t.me/+Qt_eFvkb2rliMzNh](https://t.me/+Qt_eFvkb2rliMzNh)

[Home](https://www.swifttechco.com) | [Services](https://www.swifttechco.com/services) | [Careers](https://www.swifttechco.com/careers) | [Referral Program](https://www.swifttechco.com/referral) | [Influencers](https://www.swifttechco.com/influencers) | [About](https://www.swifttechco.com/about) | [Contact](https://www.swifttechco.com/contact)

**Connect**

- Website: [swifttechco.com](https://www.swifttechco.com)
- LinkedIn: [linkedin.com/in/stephenoladoke](https://www.linkedin.com/in/stephenoladoke/)
- LinkedIn (Company): [linkedin.com/company/swift-tech-co](https://www.linkedin.com/company/swift-tech-co)
- X: [@MrOladoke](https://x.com/MrOladoke)
- Instagram: [@mr.oladoke](https://www.instagram.com/mr.oladoke/)
- Instagram (Company): [@swifttechco](https://www.instagram.com/swifttechco/)
- Organization: [github.com/Swift-Tech-Co](https://github.com/Swift-Tech-Co)
