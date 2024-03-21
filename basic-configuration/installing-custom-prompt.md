# 🕶️ Installing custom prompt

Best and easiest way to customize prompt is done by installing pre-designed prompts with `oh-my-posh`

### Installing Oh-my-posh

First thigns first, we need to install `oh-my-posh` engine designed for customizing and sharing prompt themes.

Install it with brew:

```bash
brew install jandedobbeleer/oh-my-posh/oh-my-posh
```

This will install two things:

1. `oh-my-posh` - Executable in `$(brew --prefix)/bin`
2. `themes` - The latest Oh My Posh [themes](https://ohmyposh.dev/docs/themes) in `$(brew --prefix oh-my-posh)/themes`

If you want to use a predefined theme, you can find them in `$(brew --prefix oh-my-posh)/themes`, referencing them as such will always keep them compatible when updating Oh My Posh.

{% hint style="info" %}
In case you see [strange behaviour](https://github.com/JanDeDobbeleer/oh-my-posh/issues/1287) in your shell, reload it after upgrading Oh My Posh. For example in zsh:

`brew update && brew upgrade && exec zsh`
{% endhint %}





### Installing Custom Fonts for terminal

Oh My Posh was designed to use [Nerd Fonts](https://www.nerdfonts.com/). Nerd Fonts are popular fonts that are patched to include icons. We recommend [Meslo LGM NF](https://github.com/ryanoasis/nerd-fonts/releases/download/v3.0.2/Meslo.zip), but any Nerd Font should be compatible with the standard [themes](https://github.com/JanDeDobbeleer/oh-my-posh/tree/main/themes).

```bash
oh-my-posh font install
```

#### Configure terminal for fonts

Make sure to **configure your terminal** to use the font you have installed.&#x20;

<figure><img src="../.gitbook/assets/CleanShot 2024-03-19 at 19.04.05@2x.png" alt=""><figcaption><p>Selecting Nerd Font in iTerm</p></figcaption></figure>

Nerd Fonts designed for terminals and include bunch of icons which is very handy when customizing prompt.



### Activating oh-my-posh

Adding  `eval "$(oh-my-posh init zsh)"` into `~/.zshrc`  file will active oh-my-posh but we need to wrap it in if check fot default apple terminals, as it has issues displaying  ANSI characters correctly.

{% code title="~/.zshrc" %}
```bash
# -- activate oh-my-posh (skip Apple Terminal)
if [ "$TERM_PROGRAM" != "Apple_Terminal" ]; then
  eval "$(oh-my-posh init zsh)"
fi
```
{% endcode %}

this will install default prompt theme. If you want to customize theme, we'll do it in next section below



### Customizing prompt

To customize predefined theme, first choose base theme from [themes](https://ohmyposh.dev/docs/themes) page

Let's take [catppuccin\_frappe](https://github.com/JanDeDobbeleer/oh-my-posh/blob/main/themes/catppuccin\_frappe.omp.json) as base theme:

<figure><img src="../.gitbook/assets/image (1).png" alt=""><figcaption></figcaption></figure>

1.  First make empty folder in home dir:\


    ```bash
    mkdir -p ~/.dotfiles/oh-my-posh/themes
    ```


2.  Copy base theme `json` file from `$(brew --prefix oh-my-posh)/themes` folder:\


    {% code overflow="wrap" %}
    ```bash
    cp /opt/homebrew/opt/oh-my-posh/themes/catppuccin_frappe.omp.json ~/.dotfiles/oh-my-posh/themes/basic_prompt.omp.json
    ```
    {% endcode %}



Customize theme file sections and pallete colors as you like.&#x20;

Customized `basic_prompt.omp.json` file looks like this:

{% code title="basic_prompt.omp.json" %}
```json
{
  "$schema": "https://raw.githubusercontent.com/JanDeDobbeleer/oh-my-posh/main/themes/schema.json",
  "palette": {
        "os": "#ACB0BE",
        "closer": "p:os",
        "pink": "#F8677B",
        "lavender": "#BABBF1",
        "blue":  "#8CAAEE",
        "orange": "#F3AE35"
  },
  "blocks": [
    {
      "alignment": "left",
      "segments": [
        {
          "foreground": "p:os",
          "style": "plain",
          "template": "{{.Icon}} ",
          "type": "os"
        },
        {
          "foreground": "p:blue",
          "style": "plain",
          "template": "{{ .UserName }}@{{ .HostName }} ",
          "type": "session"
        },
        {
          "foreground": "p:orange",
          "properties": {
            "folder_icon": "..\ue5fe..",
            "home_icon": "~",
            "style": "agnoster_short"
          },
          "style": "plain",
          "template": "{{ .Path }} ",
          "type": "path"
        },
        {
          "foreground": "p:pink",
          "properties": {
            "branch_icon": "\ue725 ",
            "cherry_pick_icon": "\ue29b ",
            "commit_icon": "\uf417 ",
            "fetch_status": false,
            "fetch_upstream_icon": false,
            "merge_icon": "\ue727 ",
            "no_commits_icon": "\uf0c3 ",
            "rebase_icon": "\ue728 ",
            "revert_icon": "\uf0e2 ",
            "tag_icon": "\uf412 "
          },
          "template": "{{ .HEAD }} ",
          "style": "plain",
          "type": "git"
        },
        {
          "style": "plain",
          "foreground": "p:closer",
          "template": "\uf105",
          "type": "text"
        }
      ],
      "type": "prompt"
    }
  ],
  "final_space": true,
  "version": 2
}

```
{% endcode %}

Next we need to activate our custom theme by updating `.zshrc` file `oh-my-zsh` activation section:

{% code title="~/.zshrc" %}
```bash
# -- set oh-my-posh prompt theme (skip apple terminal)
if [ "$TERM_PROGRAM" != "Apple_Terminal" ]; then
  #   eval "$(oh-my-posh init zsh)"
  eval "$(oh-my-posh init zsh --config ~/.dotfiles/oh-my-posh/themes/basic_prompt.omp.json)"
fi
```
{% endcode %}

#### **Done!**&#x20;

Enjoy your beautiful and minimalistic prompt 🥳

<figure><img src="../.gitbook/assets/CleanShot 2024-03-19 at 19.44.37@2x.png" alt=""><figcaption></figcaption></figure>

