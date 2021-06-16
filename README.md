<p align="center">
    <img src="https://cdn.svarun.dev/gh/varunsridharan/github-gitea-mirror/banner.jpg"/>
</p>

Simple Python Script To Mirror Repository / Gist From Github To Gitea

## Why ?
I am a [data hoarder.](https://www.reddit.com/r/DataHoarder/)

I am not migrating away from GitHub because I see no reason to: the platform is very useful to me, and I’d not like to lose it. What I’m trying to accomplish is a fail-safe in case something happens to GitHub which would make me lose access, be that voluntarily or involuntarily.

## ✅  Requirements
1. Python3 -- `sudo apt-get install python3`
2. [PyGithub](https://github.com/PyGithub/PyGithub) -- `pip install PyGithub`

## ⚙️Installation

### Github Clone
Just run the below cmd in your Gitea server

    git clone https://github.com/varunsridharan/github-gitea-mirror

Or you can download the source code and install it where ever you need

## 🚀 Usage

### Github Access Token Scopes
* if you want to mirror private repos then select everything under **Repo** scope
* if you want to mirror public repos then select **repo.public_repo** scope
* if you want to mirror secret Gists then select **gist** scope

### First make sure you have updated the `config.json`

| Option | Description |
| --- | --- |
| `github.username` | Your Github Username |
| `github.accesstoken` | Your Github Account's Personal Access Token |
| - | - | 
| `gitea.host` | Selfhosted Gitea URL without `/` at the end |
| `gitea.accesstoken` | Your Personal Access Token |
| `gitea.username` | Account User Name |
| `gitea.gist.prefix` | Custom Prefix For Repository When Mirroring Gists |
| `gitea.gist.surfix` | Custom Prefix For Repository When Mirroring Gists |
| - | - | 
| `repomap` | Remap A Repository To Diff User | 
| `gistsSource` | set to true to mirror all Gists Created By You| 
| `gistsStared` | set to true to mirror all Gists Stared By You| 
| `repositoryStared` | set to true to mirror all Repository Stared By You | 
| `repositorySource` | set to true to mirror all Repository Created By You | 
| `repositoryForked` | set to true to mirror all Repository Forked By You | 
| - | - |
| `local_cache.enabled` | Set to **true** to store all repostiory slugs from gitea as json |
| `local_cache.file_path` | Custom Path to store json file |

> Local Cache can come handly when running this script via cron 
> which reduces api request your selfhosted gitea instance

### Run cmd & Wait

    $ python3 mirror.py
    
    
## Cron Setup
1. Run `crontab -e`
2. `mkdir $HOME/mirrorLogs -p`
3. ``0 0 * * * /usr/bin/python3 $HOME/github-gitea-mirror/mirror.py > $HOME/github-gitea-mirror/mirrorLogs/`date +\%Y\%m\%d\%H\%M\%S`-cron.log 2>&1``

---

## 📝 Changelog
All notable changes to this project will be documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.0.0/),
and this project adheres to [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

[Checkout CHANGELOG.md](/CHANGELOG.md)

This is a fork of the [original repo](https://github.com/varunsridharan/github-gitea-mirror)
