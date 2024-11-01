# Prebuilt Caddy Docker Image with integrated Name.com DNS module

A Docker image for [Caddy](https://github.com/caddyserver/caddy) with the [Name.com](https://www.name.com) DNS provider module integrated.

## Overview

Caddy is a powerful and flexible web server, but its official Docker images do not include DNS provider modules by default. To solve ACME [DNS-01 challenges](https://letsencrypt.org/docs/challenge-types/) using your DNS providers API, you must build a custom Docker image that includes the necessary DNS provider module.

This repository automates the process of building and maintaining a Docker image of Caddy with the [`namedotcom` DNS provider module](https://github.com/caddy-dns/namedotcom) pre-installed. By using this image, you can easily leverage Name.com’s DNS services without needing to customize the Caddy base image yourself.

## Features

- __Automated Builds__: The Docker image is automatically built and published using [GitHub Actions](https://docs.github.com/en/actions) and [Renovate](https://docs.renovatebot.com), ensuring you always have access to the latest version.
- __Name.com Integration__: The `namedotcom` Caddy module is included, allowing seamless integration with Name.com’s DNS services.
- __Multi-Registry Publishing__: Images are published to both [Docker Hub](https://hub.docker.com/repository/docker/mpgirro/caddy-with-namedotcom/general) and [GitHub Container Registry (GHCR)](https://github.com/mpgirro/caddy-with-namedotcom/pkgs/container/caddy-with-namedotcom), giving you flexibility in where you pull your images from.
- __Consistent Tagging__: Images are tagged with the same version tags as the official Caddy images, except for the Windows-specific tags, ensuring compatibility and consistency across your deployments.

## Usage

Simply pull this image and use it as a drop-in replacement for the standard Caddy image if you’re utilizing Name.com as your DNS provider.

## Image Locations

- [__Docker Hub__](https://hub.docker.com/r/mpgirro/caddy-with-namedotcom): `docker pull mpgirro/caddy-with-namedotcom`
- [__GitHub Container Registry__](https://github.com/mpgirro/caddy-with-namedotcom/pkgs/container/caddy-with-namedotcom): `docker pull ghcr.io/mpgirro/caddy-with-namedotcom`

## Filing Issues

Please file issues as follows:

- Caddy in Docker: For issues related to Caddy in Docker, please report them directly in the [caddy-docker repository](https://github.com/caddyserver/caddy-docker/issues).
- Name.com Module: For issues related to the namedotcom Caddy module, please use the [namedotcom repository](https://github.com/caddy-dns/namedotcom/issues).
- Image Publishing: For issues specifically related to the image publishing (e.g., missing tags, images not being updated or published correctly), report them here in this repository.
