# incus-goad

[![Built with Ona](https://ona.com/build-with-ona.svg)](https://app.ona.com/#https://github.com/Interested-Deving-1896/incus-goad) [![KDE Eco](https://img.shields.io/badge/KDE%20Eco-certified-brightgreen?logo=kde&logoColor=white&style=flat-square)](https://eco.kde.org/) [![Blue Angel](https://img.shields.io/badge/Blue%20Angel-DE--UZ%20215-0055a4?style=flat-square)](https://www.blauer-engel.de/en/certification/criteria) [![Energy](https://api.green-coding.io/v1/ci/badge/get?repo=Interested-Deving-1896%2Fincus-goad&branch=main&workflow=eco-audit.yml)](https://metrics.green-coding.io/ci-index.html)


<!-- AI:start:what-it-does -->
_Description pending._
<!-- AI:end:what-it-does -->

## Architecture

<!-- AI:start:architecture -->
_Architecture documentation pending._
<!-- AI:end:architecture -->

## Install

<!-- Add installation instructions here. This section is yours — the AI will not modify it. -->

```bash
git clone https://github.com/Interested-Deving-1896/incus-goad.git
cd incus-goad
```

## Usage


The following commands should get you started.

```
# create the lab-hosting container
incus init images:debian/bookworm goad -c security.nesting=true

# resources - 8 CPUs, 16G of RAM, 128G of disk space
incus config set goad limits.cpu=8 limits.memory=16GiB
incus config device override goad root size=128GiB

# kvm passthrough
incus config device add goad kvm unix-char source=/dev/kvm
incus config device add goad vhost-net unix-char source=/dev/vhost-net
incus config device add goad vhost-vsock unix-char source=/dev/vhost-vsock
incus config device add goad vsock unix-char source=/dev/vsock

# start the container
incus start goad
```

Once the lab-hosting container is running, open a shell in it, clone
this project and run the `goad.sh` script.
For example:

```
# run the following commands inside the container using:
# incus exec goad bash

apt-get update
apt-get -y install git

git clone --recurse-submodules --depth=1 https://github.com/antifob/incus-goad
cd incus-goad

# deploy the "GOAD" lab - VM images are stored locally (see FAQs)
sh goad.sh GOAD local

# deploy the "GOAD-Light" lab - VM images are stored remotely
# > adds the specified simplestreams remote with the name "r"
# > you must manually edit config.auto.tfvars accordingly
# sh goad.sh GOAD-Light https://images.example.invalid/
```

## Configuration

<!-- Document configuration options here. This section is yours — the AI will not modify it. -->

## CI

<!-- AI:start:ci -->
_CI documentation pending._
<!-- AI:end:ci -->

## Mirror chain

<!-- AI:start:mirror-chain -->
This repo is maintained in [`Interested-Deving-1896/incus-goad`](https://github.com/Interested-Deving-1896/incus-goad) and mirrored through:

```
Interested-Deving-1896/incus-goad  ──►  OpenOS-Project-OSP/incus-goad  ──►  OpenOS-Project-Ecosystem-OOC/incus-goad
```

Changes flow downstream automatically via the hourly mirror chain in
[`fork-sync-all`](https://github.com/Interested-Deving-1896/fork-sync-all).
Direct commits to OSP or OOC are detected and opened as PRs back to `Interested-Deving-1896`.
<!-- AI:end:mirror-chain -->

## Contributors

<!-- AI:start:contributors -->
_Contributors pending._
<!-- AI:end:contributors -->

## Origins

<!-- AI:start:origins -->
_Original project — no upstream influences recorded._
<!-- AI:end:origins -->

## Resources

<!-- AI:start:resources -->
_No additional resource files found._
<!-- AI:end:resources -->

## Accessibility

<!-- AI:start:accessibility -->
This repo uses automated accessibility auditing via `check-accessibility.yml`.

Checks include: CODEOWNERS ownership coverage, README screen-reader compatibility,
WCAG 2.1 AA HTML compliance, audio overview (espeak-ng), and Braille output (liblouis).




Run the [Check Accessibility](https://github.com/Interested-Deving-1896/incus-goad/actions/workflows/check-accessibility.yml)
workflow to generate the first report and accessibility artifacts.
See [DOCS/accessibility.md](https://github.com/Interested-Deving-1896/incus-goad/blob/main/DOCS/accessibility.md) for the full reference.
<!-- AI:end:accessibility -->

## License

<!-- AI:start:license -->
<!-- License not detected — add a LICENSE file to this repo. -->
<!-- AI:end:license -->
