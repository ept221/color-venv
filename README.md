# color-venv
A snippet for .zshrc to add colored zsh prompt prefix for Python venv

```zsh
autoload -U colors && colors

export DEFAULT_PROMPT=$PS1

export VIRTUAL_ENV_DISABLE_PROMPT=1s
source .venv/bin/activate
precmd() {
    if [ -n "${VIRTUAL_ENV:-}" ] ; then
        export PS1="%B%{$fg[green]%}($(basename $VIRTUAL_ENV))%{$reset_color%}%b $DEFAULT_PROMPT"
    else 
        export PS1=$DEFAULT_PROMPT
    fi
}
```
