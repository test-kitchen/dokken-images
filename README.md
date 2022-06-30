# Docker images for use with kitchen-dokken

Docker images for various operating systems built specifically for use with the Test Kitchen plugin [kitchen-dokken](https://kitchen.ci/docs/drivers/dokken/). Use these images as stand-ins for full OS installations in your CI pipelines or for quick local testing.

All images are published to [Docker Hub](https://hub.docker.com/r/dokken/).

## Why Do We Need These?

Operating system vendors publish their own Docker images, but these images are very minimal. Vendor images are optimized for running applications in Docker or Kubernetes clusters. When testing Chef Infra cookbooks, we need Docker images that look like a fresh install of the OS. That means we need common OS utilities or even a complete systemd installation. These Dokken images are loaded with additional packages to make them more like a VM or cloud instance so you can quickly test without issues.
