# Installation Oh My Zsh 💻



Update the packages:
```bash
sudo apt-get update && sudo apt-get upgrade
```

Install zsh:
```bash
sudo apt install zsh
```

To check the installation of zsh: `which zsh /usr/bin/zsh` From the output you can see that zsh was successfully installed in `/usr/bin/zsh`.

Change current shell First check which shell you are currently running in with the following echo command: `echo $SHELL /bin/bash` The above output shows that the bash shell is currently used. To change the default shell, you must run the following chsh command:

```bash
chsh -s $(which zsh)
```

Log out of your current session, now when you log back into the terminal you will have a Zsh shell instead of the default bash shell.

Install and run ohmyzsh:

```bash
wget https://github.com/robbyrussell/oh-my-zsh/raw/master/tools/install.sh -O - | zsh
zsh
```

Install zsh-syntax-highlighting from github and move it to your plugins folder:

```bash
git clone https://github.com/zsh-users/zsh-syntax-highlighting.git
mv zsh-syntax-highlighting ~/.oh-my-zsh/plugins
```

Then paste the following line at the end of the ~/.zshrc file:

```bash
echo "source ~/.oh-my-zsh/plugins/zsh-syntax-highlighting/zsh-syntax-highlighting.zsh" >> ~/.zshrc
```

When entering a command in the zsh shell, it is helpful if the shell supports an autocomplete mechanism.

Install the zsh-autosuggestions plugin:

```bash
git clone https://github.com/zsh-users/zsh-autosuggestions
mv zsh-autosuggestions ~/.oh-my-zsh/custom/plugins
```

Then add the plugins to the list of plugins in the ~/.zshrc file via vim: `plugins=(git npm sudo zsh-autosuggestions vagrant)`

Now apply the change by running:

```bash
source ~/.zshrc
```

## Install fzf-tab

> [!IMPORTANT]
>
> 1. make sure [fzf](https://github.com/junegunn/fzf)  is installed
> 2. fzf-tab needs to be loaded after `compinit`, but before plugins which will wrap widgets, such as [zsh-autosuggestions](https://github.com/zsh-users/zsh-autosuggestions) or [fast-syntax-highlighting](https://github.com/zdharma-continuum/fast-syntax-highlighting)

Clone this repository to your custom directory and then add `fzf-tab` to your plugin list.

```bash
git clone https://github.com/Aloxaf/fzf-tab ${ZSH_CUSTOM:-~/.oh-my-zsh/custom}/plugins/fzf-tab
```

Add the plugin in `.zshrc`: `plugins=(git npm sudo fzf-tab zsh-autosuggestions vagrant)`

Now apply the change by running:

```bash
source ~/.zshrc
```

## Install eza

Eza is available from [deb.gierens.de](http://deb.gierens.de). The GPG public
key is in this repo under [deb.asc](/deb.asc).

First make sure you have the `gpg` command, and otherwise install it via:

```bash
sudo apt update
sudo apt install -y gpg
```

Then install eza via:

```bash
sudo mkdir -p /etc/apt/keyrings
wget -qO- https://raw.githubusercontent.com/eza-community/eza/main/deb.asc | sudo gpg --dearmor -o /etc/apt/keyrings/gierens.gpg
echo "deb [signed-by=/etc/apt/keyrings/gierens.gpg] http://deb.gierens.de stable main" | sudo tee /etc/apt/sources.list.d/gierens.list
sudo chmod 644 /etc/apt/keyrings/gierens.gpg /etc/apt/sources.list.d/gierens.list
sudo apt update
sudo apt install -y eza
```
_Note_: In strict apt environments, you may need to add the target: `echo "deb [arch=amd64 signed-by=...` 








