# 1Password CLI - Command Line Password Manager

## Table of contents
1. [Install HomeBrew (if needed)](#user-content-homebrew-installation)
1. [Install or Update gnupg (if needed)](#user-content-gnupg-installation)
1. [Install 1Password CLI](#user-content-1passwordcli-installation)
1. [Using 1Password CLI](#user-content-1passwordcli-usage)

<a name="homebrew-installation"></a>
### Install homebrew (if needed)

If brew is not installed then it can be installed via the following command:
```bash
/usr/bin/ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"
```
[Reference](https://brew.sh/)

<a name="gnupg-installation"></a>
### Install or Update gnupg (if needed)

If gnupg is not installed then it can be installed via the following command:
```bash
brew install gnupg
```

If gnupg is installed then it can be upgraded via the following command:
```bash
brew upgrade gnupg
```

<a name="1passwordcli-installation"></a>
### Install 1Password CLI

* [Download 1Password CLI](https://app-updates.agilebits.com/product_history/CLI).
* Validate 1Password CLI Signature

```bash
gpg --receive-keys 3FEF9748469ADBE15DA7CA80AC2D62742012EA22
gpg --verify op.sig op
```

**Gnupg should confirm that the binary was signed by an RSA key matching the fingerprint on the --receive-keys line (at a minimum)**

<a name="1passwordcli-usage"></a>
### Using 1Password CLI

[Reference](https://support.1password.com/command-line-getting-started/)
