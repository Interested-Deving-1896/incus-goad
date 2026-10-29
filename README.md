# incus-goad

[![AI agent ready](https://img.shields.io/badge/AI_agent-ready-2ea44f?style=flat-square)](https://github.com/Interested-Deving-1896/fork-sync-all/blob/main/DOCS/ai-agent-badges.md)
[![Open in Codex](https://img.shields.io/badge/Open_in-Codex-000000?style=flat-square&logo=openai&logoColor=white)](https://chatgpt.com/codex)
[![Open in Claude Code](https://img.shields.io/badge/Open_in-Claude_Code-d97757?style=flat-square&logo=anthropic&logoColor=white)](https://claude.ai/code)
[![Open in GitHub Copilot](https://img.shields.io/badge/Open_in-GitHub_Copilot-181717?style=flat-square&logo=githubcopilot&logoColor=white)](https://github.com/copilot)
[![Open in Cursor](https://img.shields.io/badge/Open_in-Cursor-111111?style=flat-square)](https://cursor.com/agents)
[![Use with Gemini CLI](https://img.shields.io/badge/Use_with-Gemini_CLI-4285f4?style=flat-square&logo=googlegemini&logoColor=white)](https://github.com/google-gemini/gemini-cli)
[![KDE Eco](https://img.shields.io/badge/KDE%20Eco-certified-brightgreen?logo=kde&logoColor=white&style=flat-square)](https://eco.kde.org/) [![Blue Angel](https://img.shields.io/badge/Blue%20Angel-DE--UZ%20215-0055a4?style=flat-square)](https://www.blauer-engel.de/en/certification/criteria)




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
| Contributor | Commits |
|---|---|
| [@Interested-Deving-1896](https://github.com/Interested-Deving-1896) | 25 |
| [@antifob](https://github.com/antifob) | 13 |
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
No  was found when this README was generated. Check the
[Actions tab](https://github.com/Interested-Deving-1896/incus-goad/actions) for repository-specific checks, and document an
accessibility status only when a report or workflow provides evidence for it.




See the [W3C Web Content Accessibility Guidelines (WCAG)](https://www.w3.org/WAI/standards-guidelines/wcag/)
for accessibility guidance.
<!-- AI:end:accessibility -->

## License

<!-- AI:start:license -->
<!-- License not detected — add a LICENSE file to this repo. -->
<!-- AI:end:license -->
