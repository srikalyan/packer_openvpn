## Overview

This repository contains configurations for using Packer to build an AWS AMI that define
a box that can be used as an OpenVPN server. It is based on the [docker-base][] image.

## Release Process

This repo is using [git-flow][]. Once you release and push to master you need to get the definitions
built by [Atlas][]. You only need to push to master (tags too!) to kick off a build in Atlas.

### Instance-store definitions

## Artifacts

Once Atlas is done building you can find the latest images here:

* [AWS AMIs][]
* [Virtualbox Boxes][]

For an AMI, you can find it's id by looking at the metadata in Atlas.

## Subtrees
This repo is using git subtrees to pull in dependencies. Why not submodules?
Well, they're horrible for one. Subtrees are much simpler, you don't need
to run any extra commands, just clone as usual and everything is there.

### packer-ansible subtree
Subtree for https://github.com/locationlabs/packer-ansible

To update run the following:

```
git subtree pull --prefix ansible https://github.com/locationlabs/packer-ansible master --squash
```

Always use the `master` branch of [packer-ansible][] so that you're getting the latest
released version (or use a tag).


[packer-ansible]: https://github.com/locationlabs/packer-ansible
[Atlas]: https://atlas.hashicorp.com
[git-flow]: https://github.com/nvie/gitflow
[AWS AMIs]: https://atlas.hashicorp.com/llabs/artifacts/openvpn/types/amazon.ami
[docker-base]: https://github.com/locationlabs/packer_docker-base/
