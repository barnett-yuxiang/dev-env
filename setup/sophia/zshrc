# Enable Powerlevel10k instant prompt. Should stay close to the top of ~/.zshrc.
# Initialization code that may require console input (password prompts, [y/n]
# confirmations, etc.) must go above this block; everything else may go below.
if [[ -r "${XDG_CACHE_HOME:-$HOME/.cache}/p10k-instant-prompt-${(%):-%n}.zsh" ]]; then
  source "${XDG_CACHE_HOME:-$HOME/.cache}/p10k-instant-prompt-${(%):-%n}.zsh"
fi

# If you come from bash you might have to change your $PATH.
# export PATH=$HOME/bin:/usr/local/bin:$PATH

# Path to your oh-my-zsh installation.
export ZSH="$HOME/.oh-my-zsh"

# Set name of the theme to load --- if set to "random", it will
# load a random theme each time oh-my-zsh is loaded, in which case,
# to know which specific one was loaded, run: echo $RANDOM_THEME
# See https://github.com/ohmyzsh/ohmyzsh/wiki/Themes
# ZSH_THEME="robbyrussell"
# ZSH_THEME="af-magic"
ZSH_THEME="powerlevel10k/powerlevel10k"
# update Powerlevel10k
# git -C "${ZSH_CUSTOM:-$HOME/.oh-my-zsh/custom}/themes/powerlevel10k" pull

# Set list of themes to pick from when loading at random
# Setting this variable when ZSH_THEME=random will cause zsh to load
# a theme from this variable instead of looking in $ZSH/themes/
# If set to an empty array, this variable will have no effect.
# ZSH_THEME_RANDOM_CANDIDATES=( "robbyrussell" "agnoster" )

# Uncomment the following line to use case-sensitive completion.
# CASE_SENSITIVE="true"

# Uncomment the following line to use hyphen-insensitive completion.
# Case-sensitive completion must be off. _ and - will be interchangeable.
# HYPHEN_INSENSITIVE="true"

# Uncomment one of the following lines to change the auto-update behavior
# zstyle ':omz:update' mode disabled  # disable automatic updates
# zstyle ':omz:update' mode auto      # update automatically without asking
# zstyle ':omz:update' mode reminder  # just remind me to update when it's time

# Uncomment the following line to change how often to auto-update (in days).
# zstyle ':omz:update' frequency 13

# Uncomment the following line if pasting URLs and other text is messed up.
# DISABLE_MAGIC_FUNCTIONS="true"

# Uncomment the following line to disable colors in ls.
# DISABLE_LS_COLORS="true"

# Uncomment the following line to disable auto-setting terminal title.
# DISABLE_AUTO_TITLE="true"

# Uncomment the following line to enable command auto-correction.
# ENABLE_CORRECTION="true"

# Uncomment the following line to display red dots whilst waiting for completion.
# You can also set it to another string to have that shown instead of the default red dots.
# e.g. COMPLETION_WAITING_DOTS="%F{yellow}waiting...%f"
# Caution: this setting can cause issues with multiline prompts in zsh < 5.7.1 (see #5765)
# COMPLETION_WAITING_DOTS="true"

# Uncomment the following line if you want to disable marking untracked files
# under VCS as dirty. This makes repository status check for large repositories
# much, much faster.
# DISABLE_UNTRACKED_FILES_DIRTY="true"

# Uncomment the following line if you want to change the command execution time
# stamp shown in the history command output.
# You can set one of the optional three formats:
# "mm/dd/yyyy"|"dd.mm.yyyy"|"yyyy-mm-dd"
# or set a custom format using the strftime function format specifications,
# see 'man strftime' for details.
# HIST_STAMPS="mm/dd/yyyy"

# Would you like to use another custom folder than $ZSH/custom?
# ZSH_CUSTOM=/path/to/new-custom-folder

# Which plugins would you like to load?
# Standard plugins can be found in $ZSH/plugins/
# Custom plugins may be added to $ZSH_CUSTOM/plugins/
# Example format: plugins=(rails git textmate ruby lighthouse)
# Add wisely, as too many plugins slow down shell startup.
plugins=(
    git
    poetry
    web-search
    zsh-autosuggestions
    zsh-completions
    zsh-syntax-highlighting
    zsh-history-substring-search
)
# ${ZSH_CUSTOM:-~/.oh-my-zsh/custom}/plugins
# https://python-poetry.org/docs/#zsh
# poetry completions zsh > $ZSH_CUSTOM/plugins/poetry/_poetry

# Customized by @yuli.kamakura {

# Source private config (secrets, identity info)
[[ -f ~/.zshrc.private ]] && source ~/.zshrc.private

# Config fpath completions {{

# zsh-completions config
fpath+=${ZSH_CUSTOM:-${ZSH:-~/.oh-my-zsh}/custom}/plugins/zsh-completions/src

# }} Config fpath completions

# End } Customized by @yuli.kamakura

source $ZSH/oh-my-zsh.sh

# User configuration

# export MANPATH="/usr/local/man:$MANPATH"

# You may need to manually set your language environment
# export LANG=en_US.UTF-8

# Preferred editor for local and remote sessions
# if [[ -n $SSH_CONNECTION ]]; then
#   export EDITOR='vim'
# else
#   export EDITOR='mvim'
# fi

# Compilation flags
# export ARCHFLAGS="-arch x86_64"

# Set personal aliases, overriding those provided by oh-my-zsh libs,
# plugins, and themes. Aliases can be placed here, though oh-my-zsh
# users are encouraged to define aliases within the ZSH_CUSTOM folder.
# For a full list of active aliases, run `alias`.
#
# Example aliases
# alias zshconfig="mate ~/.zshrc"
# alias ohmyzsh="mate ~/.oh-my-zsh"

# Customized by @yuli.kamakura {

# HomeBrew Config {{

# Base Flags
# curl / sqlite / zlib accumulate into LDFLAGS, CPPFLAGS, PKG_CONFIG_PATH below

# curl
export PATH="/opt/homebrew/opt/curl/bin:$PATH"
export LDFLAGS="-L/opt/homebrew/opt/curl/lib $LDFLAGS"
export CPPFLAGS="-I/opt/homebrew/opt/curl/include $CPPFLAGS"
export PKG_CONFIG_PATH="/opt/homebrew/opt/curl/lib/pkgconfig:$PKG_CONFIG_PATH"

# sqlite
export PATH="/opt/homebrew/opt/sqlite/bin:$PATH"
export LDFLAGS="-L/opt/homebrew/opt/sqlite/lib $LDFLAGS"
export CPPFLAGS="-I/opt/homebrew/opt/sqlite/include $CPPFLAGS"
export PKG_CONFIG_PATH="/opt/homebrew/opt/sqlite/lib/pkgconfig:$PKG_CONFIG_PATH"

# zlib
export LDFLAGS="-L/opt/homebrew/opt/zlib/lib $LDFLAGS"
export CPPFLAGS="-I/opt/homebrew/opt/zlib/include $CPPFLAGS"
export PKG_CONFIG_PATH="/opt/homebrew/opt/zlib/lib/pkgconfig:$PKG_CONFIG_PATH"

# Note for tcl-tk
# If you need the sqlite3_analyzer binary, it's available in the `sqlite-analyzer` formula.

# }} HomeBrew Config

# Useful Aliases {{

# Common Directory Listing
alias ll='ls -alF'  # List all files in long format, including hidden ones, and append file type indicators
alias la='ls -A'    # List all entries except for '.' and '..'
alias l='ls -CF'    # List files in columns and append file type indicators

# Android systrace
# sched freq idle am wm gfx view binder_driver hal dalvik camera input res memory
# alias st-systrace='python $ANDROID_HOME/platform-tools/systrace/systrace.py'

# Android toolchains specific versions
# alias 29_0_3_dexdump='$ANDROID_HOME/build-tools/29.0.3/dexdump'
# alias 30_0_3_dexdump='$ANDROID_HOME/build-tools/30.0.3/dexdump'

# Update global gitconfig
alias update-gitconfig-github='git config --global user.name "$GIT_USER_NAME" && git config --global user.email "$GIT_USER_EMAIL"'
alias update-gitconfig-editor-vim='git config --global core.editor "vim"'
alias update-gitconfig-default-branch='git config --global init.defaultBranch "main"'
alias update-gitconfig-color-ui='git config --global color.ui "auto"'
alias update-gitconfig-quotepath-false='git config --global core.quotepath "false"'

# }} Useful Aliases

# Useful Function {{

ggitcfg_check() {
    git --no-pager config --global -l
}

# }} Useful Function

# Config Android env {{

export ANDROID_HOME=$HOME/Library/Android/sdk
# export ANDROID_AVD_HOME=$HOME/.android/avd
export PATH=$ANDROID_HOME/platform-tools:$ANDROID_HOME/cmdline-tools/latest/bin:$PATH

# }} Config Android env

# Config Java env {{

# 1.Oracle JDK
# https://www.oracle.com/java/technologies/downloads
# export JAVA_HOME=/Library/Java/JavaVirtualMachines/jdk-17.jdk/Contents/Home
# export JAVA_HOME=/Library/Java/JavaVirtualMachines/jdk-11.jdk/Contents/Home
# export JAVA_HOME=/Library/Java/JavaVirtualMachines/jdk-1.8.jdk/Contents/Home
# export PATH=$JAVA_HOME/bin:$PATH

# 2.mvnvm
# https://mvnvm.org
# $ cat mvnvm.properties
# mvn_version=3.9.4
# Alternatively, set properties in ${HOME}/.mvnvm.properties to apply to all projects

# }} Config Java env

# Config Go env {{

# go version go1.25.7 darwin/arm64
# https://go.dev/doc/install
export GOPATH=$HOME/go
export PATH=$GOPATH/bin:$PATH
export GO111MODULE=on

# }} Config Go env

# Config Python env {{

# 1.pyenv
# https://github.com/pyenv/pyenv
# install: brew install pyenv
export PYENV_ROOT="$HOME/.pyenv"
[[ -d $PYENV_ROOT/bin ]] && export PATH="$PYENV_ROOT/bin:$PATH"
eval "$(pyenv init -)"

# 2.pyenv-virtualenv
# https://github.com/pyenv/pyenv-virtualenv
# install: $(pyenv root)/plugins/pyenv-virtualenv
eval "$(pyenv virtualenv-init -)"

# 3.poetry
# https://github.com/python-poetry/install.python-poetry.org
# https://python-poetry.org/docs/main/
# - install instructions
# - poetry completions zsh > ~/.oh-my-zsh/custom/plugins/poetry/_poetry and plugins=(... poetry)
# 3.2 uv
# curl -LsSf https://astral.sh/uv/install.sh | sh
# - uv self update
# - uv cache prune
export PATH=$HOME/.local/bin:$PATH

# }} Config Python env

# Config Node env {{

# 1.nvm
# https://github.com/nvm-sh/nvm
# Manual Upgrade, refer to the official website
export NVM_DIR="$([ -z "${XDG_CONFIG_HOME-}" ] && printf %s "${HOME}/.nvm" || printf %s "${XDG_CONFIG_HOME}/nvm")"
[ -s "$NVM_DIR/nvm.sh" ] && \. "$NVM_DIR/nvm.sh" # This loads nvm
[ -s "$NVM_DIR/bash_completion" ] && \. "$NVM_DIR/bash_completion"  # This loads nvm bash_completion

# 2.pnpm
# https://pnpm.io/
# export PNPM_HOME="$HOME/Library/pnpm"
# case ":$PATH:" in
#   *":$PNPM_HOME:"*) ;;
#   *) export PATH="$PNPM_HOME:$PATH" ;;
# esac

# 3.bun
# install: curl -fsSL https://bun.sh/install | bash
# upgrade: bun upgrade
export BUN_INSTALL="$HOME/.bun"
export PATH="$BUN_INSTALL/bin:$PATH"

# bun completions (self-registers via `compdef` at EOF, safe to source here)
[ -s "$BUN_INSTALL/_bun" ] && source "$BUN_INSTALL/_bun"

# }} Config Node env

# Config Rust env {{

# https://www.rust-lang.org/tools/install
# default install: $HOME/.zshenv and $HOME/.profile
export PATH="$HOME/.cargo/bin:$PATH"

# }} Config Rust env

# Config Ruby env {{

# rbenv
# https://github.com/rbenv/rbenv
# install: brew install rbenv ruby-build
export PATH="$HOME/.rbenv/bin:$PATH"
eval "$(rbenv init -)"

# }} Config Ruby env

# Config dev-garage {{

# Commonly used shell scripts and command-line tools
# https://github.com/barnett-yuxiang/dev-garage
export PATH="$HOME/repo_projects/toolkit/dev-garage:$PATH"

# }} Config dev-garage

# Config p10k theme {{

# To customize prompt, run `p10k configure` or edit ~/.p10k.zsh.
[[ ! -f ~/.p10k.zsh ]] || source ~/.p10k.zsh

# }} Config p10k theme

# Config starship.rs {{

# https://starship.rs/
# Add the following to the end of ~/.zshrc
# eval "$(starship init zsh)"

# }} Config starship.rs

# Config auto-added by application installers {{

# 1.Tools
# Added by Antigravity
# export PATH="$HOME/.antigravity/antigravity/bin:$PATH"

# 2.Docker
# The following lines have been added by Docker Desktop to enable Docker CLI completions.
fpath=(/Users/sophia/.docker/completions $fpath)
autoload -Uz compinit
compinit
# End of Docker CLI completions

# }} Config auto-added by application installers

# Config Top PATH {{

# include: yt-dlp_macos
# include: repo // aosp
export PATH="$HOME/bin:$PATH"

# }} Config Top PATH

# End } Customized by @yuli.kamakura
