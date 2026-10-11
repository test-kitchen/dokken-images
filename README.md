# Docker images for use with kitchen-dokken

Docker images for various operating systems built specifically for use with the Test Kitchen plugin [kitchen-dokken](https://kitchen.ci/docs/drivers/dokken/). Use these images as stand-ins for full OS installations in your CI pipelines or for quick local testing.

All images are published to [Docker Hub](https://hub.docker.com/r/dokken/) and [GitHub Container Registry](https://github.com/orgs/test-kitchen/packages?repo_name=dokken-images).

## Why Do We Need These?

Operating system vendors publish their own Docker images, but these images are very minimal. Vendor images are optimized for running applications in Docker or Kubernetes clusters. When testing Chef Infra cookbooks, we need Docker images that look like a fresh install of the OS. That means we need common OS utilities or even a complete systemd installation. These Dokken images are loaded with additional packages to make them more like a VM or cloud instance so you can quickly test without issues.

## Using the Images

Point a kitchen-dokken platform at an image, set `pid_one_command` to the image's systemd binary, and run the container privileged:

```yaml
driver:
  name: dokken
  privileged: true

transport:
  name: dokken

provisioner:
  name: dokken
  product_name: cinc

platforms:
  - name: almalinux-10
    driver:
      image: dokken/almalinux-10
      pid_one_command: /usr/lib/systemd/systemd

  - name: ubuntu-24.04
    driver:
      image: dokken/ubuntu-24.04
      pid_one_command: /usr/lib/systemd/systemd
```

kitchen-dokken runs a sleep loop as pid 1 unless you set `pid_one_command`, so cookbooks that manage services need it, along with `privileged: true`; without it systemd can't mount its API filesystems and exits at once. The [Available Images](#available-images) table lists a working path for each image. `product_name: cinc` installs [Cinc Client](https://cinc.sh/), which needs no license acceptance in CI; leave it out to use Chef Infra Client.

Every image is built for `linux/amd64` and `linux/arm64` and published under two names:

- Docker Hub: `dokken/<image>`, for example `dokken/debian-13`
- GitHub Container Registry: `ghcr.io/test-kitchen/dokken/<image>`

Each image carries these tags:

| Tag | Updated |
| --- | --- |
| `latest`, `main` | On every merge to `main` and every nightly rebuild |
| `nightly` | By the nightly rebuild, scheduled for 00:00 UTC (GitHub often starts it later) |
| `sha-<short commit>` | On every build of that commit of `main`, so nightly rebuilds keep moving it until the next merge |

The images are rebuilt every night so their packages stay current. Pull requests build the images but never push them.

## Available Images

| Image | Base image | `pid_one_command` | Notes |
| --- | --- | --- | --- |
| `almalinux-8` | `almalinux:8` | `/usr/lib/systemd/systemd` | |
| `almalinux-9` | `almalinux:9` | `/usr/lib/systemd/systemd` | |
| `almalinux-10` | `almalinux:10` | `/usr/lib/systemd/systemd` | |
| `amazonlinux-2` | `amazonlinux:2` | `/usr/lib/systemd/systemd` | Past vendor end of life |
| `amazonlinux-2023` | `amazonlinux:2023` | `/usr/lib/systemd/systemd` | |
| `centos-stream-9` | `quay.io/centos/centos:stream9` | `/usr/lib/systemd/systemd` | |
| `centos-stream-10` | `quay.io/centos/centos:stream10-development` | `/usr/lib/systemd/systemd` | Built from the `stream10-development` tag |
| `debian-12` | `debian:bookworm` | `/usr/lib/systemd/systemd` | |
| `debian-13` | `debian:trixie` | `/usr/lib/systemd/systemd` | |
| `debian-14` | `debian:forky` | `/usr/lib/systemd/systemd` | Pre-release (Debian testing) |
| `fedora-43` | `fedora:43` | `/usr/lib/systemd/systemd` | |
| `fedora-44` | `fedora:44` | `/usr/lib/systemd/systemd` | |
| `fedora-45` | `fedora:45` | `/usr/lib/systemd/systemd` | Pre-release |
| `fedora-latest` | `fedora:latest` | `/usr/lib/systemd/systemd` | Tracks `fedora:latest` |
| `opensuse-leap-16.0` | `opensuse/leap:16.0` | `/usr/lib/systemd/systemd` | |
| `rockylinux-8` | `rockylinux:8` | `/usr/lib/systemd/systemd` | |
| `rockylinux-9` | `rockylinux:9` | `/usr/lib/systemd/systemd` | |
| `rockylinux-10` | `rockylinux/rockylinux:10` | `/usr/lib/systemd/systemd` | |
| `oraclelinux-7` | `oraclelinux:7` | `/usr/lib/systemd/systemd` | Paid extended support only |
| `oraclelinux-8` | `oraclelinux:8` | `/usr/lib/systemd/systemd` | |
| `oraclelinux-9` | `oraclelinux:9` | `/usr/lib/systemd/systemd` | |
| `oraclelinux-10` | `oraclelinux:10` | `/usr/lib/systemd/systemd` | |
| `ubuntu-18.04` | `ubuntu:18.04` | `/lib/systemd/systemd` | Ubuntu Pro (ESM) only |
| `ubuntu-20.04` | `ubuntu:20.04` | `/usr/lib/systemd/systemd` | Ubuntu Pro (ESM) only |
| `ubuntu-22.04` | `ubuntu:22.04` | `/usr/lib/systemd/systemd` | |
| `ubuntu-24.04` | `ubuntu:24.04` | `/usr/lib/systemd/systemd` | |
| `ubuntu-26.04` | `ubuntu:26.04` | `/usr/lib/systemd/systemd` | |
| `ubuntu-26.10` | `ubuntu:26.10` | `/usr/lib/systemd/systemd` | Pre-release |

## Support Policy

An image is retired once its vendor stops supporting the release, including Debian LTS. Retiring an image removes it from the build; its tags stay on both registries but are no longer rebuilt or patched, so move to a supported release.

A few older releases that cookbooks still commonly test against stay in the build past that point while they keep building. The Notes column marks them as past end of life, paid extended support only, or Ubuntu Pro (ESM) only. They are retired as soon as they stop building.

Images for releases that are still in development, marked "Pre-release", are added early so cookbooks can start testing against them. Expect them to break while the distribution changes underneath them.

## Retired Images

| Image | Last built | Move to |
| --- | --- | --- |
| `debian-11` | 2026-08-27 | `debian-12` or `debian-13` |
| `fedora-41` | 2026-08-27 | `fedora-43` or `fedora-44` |
| `fedora-42` | 2026-08-27 | `fedora-43` or `fedora-44` |
| `opensuse-leap-15` | 2026-01-17 | `opensuse-leap-16.0` |
| `opensuse-leap-15.6` | 2026-01-17 | `opensuse-leap-16.0` |
| `ubuntu-16.04` | 2026-08-27 | `ubuntu-24.04` or `ubuntu-26.04` |
| `ubuntu-25.04` | 2026-08-27 | `ubuntu-26.04` |
| `ubuntu-25.10` | 2026-08-27 | `ubuntu-26.04` |

## Contributing

To add an image:

1. Copy the Dockerfile of the closest existing image into a new directory named after the image, such as `fedora-46/Dockerfile`.
2. Change the `FROM` line and the `org.opencontainers.image.description` label. Keep the `BUILD_DATE` and `VCS_REF` build arguments, the labels, and the step that masks systemd units which don't work in a container.
3. Add the directory name to the `os-with-arm64` matrix in [.github/workflows/main.yaml](.github/workflows/main.yaml).
4. Add a row to the [Available Images](#available-images) table.

To retire an image, delete its directory, its matrix entry and its table row, and add it to [Retired Images](#retired-images).

A pull request builds every image for both architectures without pushing, so a green run means the new image builds.
