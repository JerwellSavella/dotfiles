# Settings

- Terminal: Just the simple Gnome, out of the box terminal :)
- zsh or bash (it's alright, simple and fast is the goal)
- powerlevel10k (Personal Computer)
- starship (Work machine)
- nerdFont
- Plugins
	- zsh-autosuggestions
	- zsh-syntax-highlighting
- Color Theme: Gogh


## Installation

1. Install zsh (If you want)
- Install using:  ```sudo install zsh``` 
- Check your default shell using ```echo $0```
- Change to default shell to zsh using ```chsh```
- Choose number 2 when being prompt by zshell to populate your .zshrc file with recommended configuration

2. Installation of powerlevel10k 
- ```git clone --depth=1 https://github.com/romkatv/powerlevel10k.git "${ZSH_CUSTOM:-$HOME/.oh-my-zsh/custom}/themes/powerlevel10k"```
- Add ```powerlevel10k/powerlevel10k``` to ```.zshrc``` file

3. Installation of starship (when using bash)
- ```sudo curl -sS https://starship.rs/install.sh | sh ```
- Add following line to the end of the file ```.bashrc``` ```eval "$(starship init bash)```
- Run: ```~/.bashrc```
