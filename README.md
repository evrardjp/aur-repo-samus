# Kubernetes Packages
[![Build Status](https://travis-ci.com/evrardjp/aurci.svg?branch=k8s)](https://travis-ci.com/evrardjp/aurci)

Use [Travis CI](https://travis-ci.com/evrardjp/aurci) for building and packaging a few [AUR](https://aur.archlinux.org) packages and deploy them to [GitHub Releases](https://github.com/evrardjp/aurci/releases) so it can be used as repository in [Arch Linux](https://www.archlinux.org).

## Use repository

To use as custom repository in [Arch Linux](https://www.archlinux.org), add to file `/etc/pacman.conf`:

```
[aur-k8s]
SigLevel = Optional TrustAll
Server = https://github.com/evrardjp/aurci/releases/download/k8s
```

Then on the command line:

```
pacman -Sy            # Refresh package database.
pacman -Sl aur-k8s  # Show packages in repository.
pacman -S {package}   # Install a package.
```

**NOTE:** List of currently maintained packages can change at any moment.
Check pkglist file for the packages list.

## Forking repository

For build the [AUR](https://aur.archlinux.org) packages of your election fork this repository and enable [Travis CI](https://travis-ci.com):

  - Fork this GitHub repository and edit `pkglist`.
  - Generate a personal access token with scope `public_repo`.
  - Enable Travis CI for your new forked repository.
  - In Travis CI repository settings disable build pull request updates, for security.
  - In Travis CI repository settings declare one environment variable:
    - `GITHUB_TOKEN`: The previously created personal access token, disable display value.
  - Optionally, enable a cron job in Travis CI repository settings.
