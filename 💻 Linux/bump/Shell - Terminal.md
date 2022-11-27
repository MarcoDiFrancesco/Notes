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