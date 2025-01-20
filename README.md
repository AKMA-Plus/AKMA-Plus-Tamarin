# 5G AKMA-PLUS

## Hardware Requirements
* Memory: 16GB RAM (minimum), 32GB recommended
## Build dependencies

* OS: Ubuntu 20.04 LTS.
* [tamarin-prover 1.8.0](https://tamarin-prover.com/)
### Install tamarin-prover
Use the following command(s) to install the required tools and set environment
```sh
apt update
apt-get install -y build-essential curl file git maude python-is-python3
# Install Homebrew, input Enter when required
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
# Once you see '==> Installation successful!' in the output, 'Homebrew' is installed. Otherwise, you should reinstall 'Homebrew'
# set environment
export PATH="/home/linuxbrew/.linuxbrew/bin:$PATH"
export MANPATH="/home/linuxbrew/.linuxbrew/share/man:$MANPATH"
export INFOPATH="/home/linuxbrew/.linuxbrew/share/info:$INFOPATH"
# Check Brew is working fine. You can see 'Your system is ready to brew.' in the output.
brew doctor
# install tamarin-prover
brew install tamarin-prover/tap/tamarin-prover
```

## Prove manually
run tamarin-prover
```sh
export LANG=en_US.UTF-8
chmod +x akma_oracle
tamarin-prover interactive AKMA_plus.spthy --derivcheck-timeout=100 --quit-on-warning --auto-sources
```
This will take some time. After completing, you can see

>Finished loading theories ... server ready at 
>
>    http://127.0.0.1:3001

Point your browser to http://localhost:3001, you can start to prove lemma.

## Auto prove
You can replace *** with a specific lemma
```sh
export LANG=en_US.UTF-8
chmod +x akma_oracle
tamarin-prover AKMA_plus.spthy --derivcheck-timeout=100 --quit-on-warning --auto-sources --prove=***
```