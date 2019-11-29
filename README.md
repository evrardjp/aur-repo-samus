# aurci

Use [Travis CI] for building and packaging a few [AUR] packages and deploy them
to GitHub Releases so it can be used as repository in [Arch Linux].

## Forking repository

For build the [AUR] packages of your election fork this repository and enable
[Travis CI]:

```
- Fork this GitHub repository and edit `pkglist`.
- Generate a personal access token with scope `public_repo`.
- Enable Travis CI for your new forked repository.
- In Travis CI repository settings disable build pull request updates, for security.
- In Travis CI repository settings declare one environment variable:
- `GITHUB_TOKEN`: The previously created personal access token, disable display value.
- Optionally, enable a cron job in Travis CI repository settings.
```

## Use repository

For user-specific instructions enable `gh-pages` on your fork, or check [here]
for generic ones.

[Arch Linux]: https://www.archlinux.org/
[AUR]:        https://aur.archlinux.org/
[here]:       https://localnet.github.io/aurci/
[Travis CI]:  https://travis-ci.com/
