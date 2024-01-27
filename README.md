# alma9-py3-devcontainer

# Copyright and License

This container image is based on AlmaLinux 9, see their license details for more information.

- https://almalinux.org/p/the-almalinux-os-licensing-policy/

The Dockerfile and other contents of **this repo only** are licensed as follows:

Copyright (c)2024 David L. Armstrong

See included 'LICENSE.txt' file for license details

# Description
AlmaLinux 9 Container Image intended for Devcontainer use in Python3 development

# Included functionality

## Python3 development

- Alma9 python3, pip3
- virtualenv

## Devcontainer prereqs

- findutils (for xargs)
- git
- tar

## Docker CE

For rebuilding itself - use the official Docker CE distribution

## local non-privileged user

A 'luser' account is created to help maintain the immutable CM environment.
This account is granted full sudo access with NOPASSWD so changes can be made through sudo without resistance.

