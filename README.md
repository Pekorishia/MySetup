# MySetup
My workspace setup, including git alias, PS1 modification, tmux.conf, etc.


## Git Setup
First install git

```
$ sudo apt install git
```

Then config the global credentials

```
$ git config --global user.name "John Doe"
$ git config --global user.email johndoe@example.com
```

Finally, follow this tutorial in order to set the SSH key

https://help.github.com/en/github/authenticating-to-github/generating-a-new-ssh-key-and-adding-it-to-the-ssh-agent

## Terminal appearence (PS1)
Just update your `~/.bashrc` file with the line bellow:

```
parse_git_branch() {
 git branch 2> /dev/null | sed -e '/^[^*]/d' -e 's/* \(.*\)/(\1)/'
}
if [ "$color_prompt" = yes ]; then
 PS1='${debian_chroot:+($debian_chroot)}\[\033[01;90m\]\u:\[\033[01;94m\]\w\[\033[01;95m\] $(parse_git_branch)\$ \[\033[00m\] '
else
 PS1='${debian_chroot:+($debian_chroot)}\u:\w $(parse_git_branch)\$ '
fi
unset color_prompt force_color_prompt
```

It includes the git branch name when there is a git repository.

## Git Alias
Include in your `~/.bashrc` file the lines below:

```
# some git alias commands
alias gs="git status"
alias ga="git add"
alias gc="git commit"
alias gb="git branch"
alias gco="git checkout"
alias gst="git stash"
alias gm="git merge"
alias gr="git rebase"
alias gd="diff --color --color-words --abbrev"
alias gbl="git blame"
```

## Tmux setup
first install Tmux
```
$ sudo apt install tmux
```

And just copy tmux.conf content to your `~/.tmux.conf` file

If you wish to change any set color, just run the `tmuxcolours.sh` and look for the color that you wish for.

```
$ chmod +x tmuxcolours.sh

$ ./tmuxcolours.sh
```

## Ruby setup

Just install RVM

https://github.com/rvm/ubuntu_rvm

And use the RVM to install the ruby version that you wish to work with

``` 
$ rvm install 2.5.8
```


## Docker config

First install Docker Engine

https://docs.docker.com/engine/install/ubuntu/

Then follow the post-install steps to avoid using "sudo" with docker

https://docs.docker.com/engine/install/linux-postinstall/

Finally, install Docker Compose

https://docs.docker.com/compose/install/


## Sublime setup
Follow this setup recommendations

https://mattbrictson.com/sublime-text-3-recommendations

And also include in the settings file (Preferences > settings) this line:
```
{
  "draw_white_space": "all"
}
```

## VS Code setup
In case the rest of the team use VS Code for remote pair-programming, then follow this recommended setup

https://medium.com/better-programming/code-like-a-pro-tooling-to-supercharge-vs-code-for-ruby-bf2ae61df5e3

And install VS Code live share plug-in

https://visualstudio.microsoft.com/services/live-share/


