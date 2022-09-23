# Shell - Terminal
## Terminal emulator
*urxvt* is the program I'm currently using as a terminal emulator

*urxvtd* demon is sourced on *.zshenv*, *urxvtc* is opened to get a new terminal emulator.

## Shell
*extra/zsh* is the package used as shell

*aur/oh-my-zsh-git* is a zsh extension

*/usr/share/oh-my-zsh/custom/plugins/* is the directory containing plugins

## WSL
oh-my-zsh installed in *$HOME/.oh-my-zsh* using:

```bash
sudo sh -c "$(curl -fsSL [https://raw.githubusercontent.com/robbyrussell/oh-my-zsh/master/tools/install.sh](https://raw.githubusercontent.com/robbyrussell/oh-my-zsh/master/tools/install.sh))"
```

## Tmux
`tmux` can be used for remote long sessions. It can spawn sessions that do not close when exiting.

Commands:
- `tmux ls` to list sessions
- `tmux a -t 0` to attach to session 0

Shortcuts [link](https://gist.github.com/MohamedAlaa/2961058#list-all-shortcuts):
- `C-b d` to detach from session