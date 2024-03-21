# 🧩 Installing Plugins

## Installing Oh-My-ZSH Plugin

Oh My Zsh is a delightful, open source, community-driven framework for managing your Zsh configuration. It comes bundled with thousands of helpful functions, helpers, plugins, themes, and a few things.

{% code overflow="wrap" %}
```bash
# Oh My Zsh
sh -c "$(curl -fsSL https://raw.github.com/ohmyzsh/ohmyzsh/master/tools/install.sh)"
```
{% endcode %}



## Installing ZPlug

ZPlug is a plugin manager for ZSH

```bash
# zplug
brew install zplug
```

Net you need to configure zplug to autoload plugins on session start.

Configuring zplug is done vie `.zshrc` file in home directory

{% code title="~/.zshrc" %}
```bash
export ZSH=~/.oh-my-zsh

# Zplug Config
source $ZSH/oh-my-zsh.sh
export ZPLUG_HOME=/opt/homebrew/opt/zplug
source $ZPLUG_HOME/init.zsh

# -- zplug plugins (if you want additional plugins add lines in this section)
zplug "mafredri/zsh-async", from:github


# load zplug
zplug load

# Install plugins if there are plugins that have not been installed
if ! zplug check --verbose; then
    printf "Install? [y/N]: "
    if read -q; then
        echo; zplug install
    fi
fi

```
{% endcode %}



## Syntax highlighting

<figure><img src="../.gitbook/assets/1XItfmpUtwxZP7uTwt8P1ag.gif" alt=""><figcaption></figcaption></figure>

Add syntax highlighting with installing zplug plugin.

Add source in `~/.zshrc` zplug plugins section

{% code title="~/.zshrc" %}
```bash
# -- zplug plugins (if you want additional plugins add lines in this section)
...
zplug "zdharma/fast-syntax-highlighting", as:plugin, defer:2
```
{% endcode %}



## Auto suggestions

Get suggestions and completion based on your history with [zsh-autosuggestions](https://github.com/zsh-users/zsh-autosuggestions).

<figure><img src="../.gitbook/assets/CleanShot 2024-03-19 at 13.02.03.gif" alt=""><figcaption></figcaption></figure>

Add plugin source in `~/.zshrc` zplug plugins section

{% code title="" %}
```bash
# -- zplug plugins (if you want additional plugins add lines in this section)
...
zplug "zsh-users/zsh-autosuggestions", as:plugin, defer:2
```
{% endcode %}
