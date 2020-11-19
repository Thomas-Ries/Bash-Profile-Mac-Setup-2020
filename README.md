# Bash-Profile-Mac-Setup-2020

# MAC SETUP

1. Installer Iterms2 (terminal Mac alternatif)
2. Installer Xcode
3. Installer vscode 
4. Installer clean my mac 

# First Steps
- brew install cowsay
- brew install fortune

# Passer sur un autre shell

1. which shell : renvoie : /usr/local/bin/bash 
2. sudo nano /etc/shells

# Dans nano

1. taper en haut de la liste des shell autorisées : /usr/local/bin/bash 

# Dans le terminal

1. chsh -s /usr/local/bin/bash → (change le bash par défaut)

# Voir sur quel shell je tourne

echo $SHELL

```bash
HOST_NAME=Tom

shopt -s autocd
shopt -s histappend

export PATH=$PATH:$HOME/bin

export HISTSIZE=5000
export HISTFILESIZE=10000

bind '"\e[A": history-search-backward'
bind '"\e[B": history-search-forward'

export CLICOLOR=1
export LSCOLORS=GxFxCxDxBxegedabagaced

txtred='\e[0;31m' # Red
txtgrn='\e[0;32m' # Green
bldgrn='\e[1;32m' # Bold Green
bldpur='\e[1;35m' # Bold Purple
txtrst='\e[0m'    # Text Reset

emojis=("👾" "🌐" "🎲" "🌍" "🐉" "🌵")

EMOJI=${emojis[$RANDOM % ${#emojis[@]} ]}

print_before_the_prompt () {
    dir=$PWD
    home=$HOME
    dir=${dir/"$HOME"/"~"}
    printf "\n $txtred%s: $bldpur%s $txtgrn%s\n$txtrst" "$HOST_NAME" "$dir" "$(vcprompt)"
}

PROMPT_COMMAND=print_before_the_prompt
PROMPT_COMMAND="history -a; history -c; history -r; $PROMPT_COMMAND"
PS1="$EMOJI >"

fortune | cowsay -f tux
```
