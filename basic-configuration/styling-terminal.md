---
description: >-
  To style terminal colors and set fancy prompt you need to goes through few
  steps of configuration and installing plugins
---

# 🖌️ Styling terminal



## Getting rid of ugly title bar

Go to `Preferences` -> `Appearance` -> `General` ->  `Theme`: **Minimal**

<figure><img src="../.gitbook/assets/CleanShot 2024-03-19 at 11.37.12@2x.png" alt=""><figcaption></figcaption></figure>

<figure><img src="../.gitbook/assets/1OLWAQf2Vw-MgkcGWAjOQ-A.gif" alt=""><figcaption><p>Before</p></figcaption></figure>

<figure><img src="../.gitbook/assets/1CVjNim2kFu7mA5CtI_Pnow.gif" alt=""><figcaption><p>After</p></figcaption></figure>

You can make the tab outline less prominent with:

iTerm `Preferences` -> `Advanced`

Set the value of tab outline in minimal theme to `0.1`

{% hint style="info" %}
Filter advanced settings with keyword:&#x20;

`in the minimal theme how prominent should the tab outline be`?
{% endhint %}

<figure><img src="../.gitbook/assets/CleanShot 2024-03-19 at 11.44.17@2x.png" alt=""><figcaption></figcaption></figure>



## Install iTerm Snazzy Theme

Run this command to download iTerm Snazzy color scheme:

{% code overflow="wrap" lineNumbers="true" %}
```bash
(curl -Ls https://raw.githubusercontent.com/sindresorhus/iterm2-snazzy/main/Snazzy.itermcolors > /tmp/Snazzy.itermcolors && open /tmp/Snazzy.itermcolors)
```
{% endcode %}

After downloading theme, set it in iTerm Preferences:

`Profiles` -> `Colors` -> `Color Presets`: **Snazzy**

<figure><img src="../.gitbook/assets/CleanShot 2024-03-19 at 12.30.18@2x.png" alt=""><figcaption></figcaption></figure>

{% hint style="info" %}
Pro tip: If you don’t like this theme, you can probably find your favorite theme here: [https://iterm2colorschemes.com](https://iterm2colorschemes.com/)
{% endhint %}











<table><thead><tr><th width="180">Role</th><th>Capabilities</th></tr></thead><tbody><tr><td>Administrator</td><td>Has all admin privileges</td></tr><tr><td>Editor</td><td>Can edit posts</td></tr><tr><td>Viewer</td><td>Can only view posts</td></tr><tr><td>Guest</td><td>Can only view posts they are inivted to</td></tr></tbody></table>
