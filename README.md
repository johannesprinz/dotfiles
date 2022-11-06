# dotfiles

Source of my dotfiles and install scripts for them

## How I got here

```bash
# Setup dedicated SSH key
ssh-keygen -t ed25519 -C "1687127+johannesprinz@users.noreply.github.com"
# Enter file in which to save the key (/home/johannesprinz/.ssh/id_ed25519): id_ed25519Private

# Clone and setup repo
mkdir .dotfiles
git clone git@github.com:johannesprinz/dotfiles.git .dotfiles --bare
alias dotgit='/usr/bin/git --git-dir=$HOME/.dotfiles/ --work-tree=$HOME'
dotgit config --local status.showUntrackedFiles no
dotgit config user.email 1687127+johannesprinz@users.noreply.github.com
dotgit config core.sshCommand "ssh -i ~/.ssh/id_ed25519Private"
```

## How I installed and set default shell to zsh

```bash
sudo apt update
sudo apt install zsh
zsh --version
chsh -s $(which zsh)
```

## To do

- [ ] Configure zshrc to use better prompt with git context
- [ ] Find out when to use rc vs profile
- [ ] Backup profile
- [ ] Create installer that automates setup by using a simple
      ``` bash
      curl -fsSLO https://raw.githubusercontent.com/johannesprinz/dotfiles/main/install.sh
      chmod +x ./install.sh
      ./install.sh
      ```