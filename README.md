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
