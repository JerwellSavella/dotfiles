# Personal Configuration for terminal workflow

## Tools use:

- Bash and ZSH (Bash is for work and ZSH for my computer, but for convenience I modified my .bashrc file to be compatible for both)
- STOW for symlinking and convenience of loading my existing configuration, I recommend reading the documentation and on how to use and implement this Stow, it's nice :)
- powerlevel10k
- zsh-autosuggestions
- zsh-syntax-highlighting
- Gogh Theme


## Guide

Prerequisites
1. Install ZSH
2. Install GNU Stow
3. Clone the dotfiles repository

Setup
1. Stow the bash configuration: `stow -d ~/Github/dotfiles -t ~ bashrc`
2. Install Oh My Zsh. Install it before stowing the zshrc or OMZ config, so the ~/.oh-my-zsh directory exists first.
3. Stow the Oh My Zsh configuration `stow -d ~/Github/dotfiles -t ~ oh-my-zsh`
4. Install ZSH plugins (zsh-autosuggestions and zsh-syntax-highlighting): 
- `git clone https://github.com/zsh-users/zsh-autosuggestions ${ZSH_CUSTOM:-~/.oh-my-zsh/custom}/plugins/zsh-autosuggestions`
- `git clone https://github.com/zsh-users/zsh-syntax-highlighting.git ${ZSH_CUSTOM:-~/.oh-my-zsh/custom}/plugins/zsh-syntax-highlighting`
- add those plugins to .zshrc file: `plugins=(git zsh-autosuggestions zsh-syntax-highlighting)`
5. Install Powerlevel10k: `git clone --depth=1 https://github.com/romkatv/powerlevel10k.git ~/powerlevel10k`
6. Stow the ZSH and Powerlevel10k configurations: `stow -d ~/Github/dotfiles -t ~ zshrc` and `stow -d ~/Github/dotfiles -t ~ powerlevel10k`
7. Apply the configuration: `source ~/.zshrc`

## NVIM with LazyVim Configuration Installation
- Download the Latest version of neovim from github repository, I use nvim-linux-x86_64.tar.gz and Extract: `tar xzvf nvim-linux-x86_64.tar.gz`
- Move the nvim-linux-x86_64 file from Download to /opt/ folder: `sudo mv ~/Downloads/nvim-linux-x86_64 /opt/` 
- Add this line in the bottom of your .zshrc file: `export PATH="$PATH:/opt/nvim-linux-x86_64/bin"`
- Refresh your .zshrc or .bashrc if you use that: `source ~/.zshrc`

- Loading your own nvim configuration with lazyVim already configured files that is available here as well, 
- Stow nvim file in this repository: `stow -d ~/Github/dotfiles -t ~ nvim`
- Enter `nvim` command in terminal and see if the configuration is loaded (Note: Download xclip and ripgrep to your system for yanking functionality to work)


## Install terminal theme configuration
- Install Gogh Theme: `bash -c  "$(wget -qO- https://git.io/vQgMr)"`
- Pick 155 which is the Gruvbox Material Dark theme (My personal favorite :) ) 
- Right Click terminal, Preferences, and choose that Gruvbox Material Dark as default


## Font Installation
- Install font in MesloLGS NF font in: https://github.com/romkatv/powerlevel10k#meslo-nerd-font-patched-for-powerlevel10k
- Right click terminal and under Profile click the custom font and pick the MesloLGS NF






