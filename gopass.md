# gopass - Command Line Password Manager

These instructions are for macOS Sierra, GnuPG (gpg) 2.2.1, and Git 2.15.0.

**gopass** is a command line password manager written in go and represents an improvement over **pass**.  **gopass** supports the following useful features:
 * Structured secrets using YAML for additional metadata
 * Team secret sharing via git

For a more detailed description of the **gopass** feature see [here](https://www.justwatch.com/gopass/docs/#features).

## Table of contents
1. [Install homebrew (if needed)](#user-content-homebrew-installation)
1. [Install gnupg2 (if needed)](#user-content-gnupg2-installation)
1. [Install git (if needed)](#user-content-git-installation)
1. [Install gopass](#user-content-gopass-installation)
1. [Generate a GnuPG Key Pair](#user-content-key-generation)
1. [Create a Vault](#user-content-vault-creation)
1. [Insert a Login](#user-content-login-creation)
1. [Show a Login](#user-content-login-show)
1. [Copy a Login to the Clipboard](#user-content-login-copy)

<a name="homebrew-installation"></a>
### Install homebrew

If brew is not installed then it can be installed via the following command:
```bash
/usr/bin/ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"
```
[Reference](https://brew.sh/)

<a name="gnupg2-installation"></a>
### Install gnupg2

If gnupg2 is not installed then it can be installed via the following command:
```bash
brew install gnupg2
```

<a name="git-installation"></a>
### Install git

If git is not installed then it can be installed via the following command:
```bash
brew install git
```

<a name="gopass-installation"></a>
### Install gopass 

```bash
brew tap justwatchcom/gopass
brew install gopass
```

<a name="key-generation"></a>
### Generate a GnuPG Key Pair 

List current gpg keys:
```bash
gpg --list-keys
```

Generate a gpg key-pair:
```bash
gpg --full-generate-key
```
 * Select (1) RSA and RSA (default).
 * Select 4096 bit keysize.
 * Configure the key to not expire.
 * Add a name for the key.
 * Add an email address for the key.
 * Add a comment for the key, such as "Storage Key."

<a name="vault-creation"></a>
### Create a Vault

**gopass** stores vaults by default in the ~/.password-store/ folder.  This can be overriden and considered to be the vault name.

```bash
gopass init --path ~/.gopass/.vaultname --nogit
```

**-nogit** is supplied because there is currently a git init failure with the latest version of **gopass** downloaded from **brew**.

<a name="login-creation"></a>
### Insert a Login

The **insert** verb is used to create new logins in **gopass**.  If you want to insert additional metadata then use the **-m** interactive option.  Entries are saved one per file with a **gpg** extension under your vault folder (~/.password-store or ~/.gopass/.vaultname).  When storing additional metadata via the **-m** interactive option, supply additional metadata one per line.
```bash
gopass insert WebsiteDomain/UserName
gopass insert -m WebsiteDomain/UserName
```

<a name="login-display"></a>
### Show a Login

The **show** verb is used to display a specific login entry in the secret stores filesystem hierarchy. If a fullpath to an entry is not specified then the secret store will show all matching secrets and give you the option to select the secret you wanted.
```bash
gopass
gopass show EntryName
```

<a name="login-copy"></a>
### Copy a Login to the Clipboard

The **-c** argument is used to copy the specific login entry in the secret store into the clipboard for 45-seconds. For secret entries with additional metadata, **gopass** will copy out the first line of a multiline entry. Therefore by convention it is advised to store the password on the first line of your secret entries.
```bash
gopass -c EntryName
```
