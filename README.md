# lazygit-tokyonight

Tokyonight theme for LazyGit

## Screenshots

![alt](/assets/lazygit.png)
![alt](/assets/tokyonight.png)
![alt](/assets/help.png)
![alt](/assets/menu.png)

## Installation

Prerequisites:

- [LazyGit](https://github.com/jesseduffield/lazygit)
- [Delta (optional)](https://github.com/dandavison/delta)
- [Bat (optional)](https://github.com/sharkdp/bat)

## Apply theme

Linux

```bash
cp tokyonight/night.yaml ~/.config/lazygit/config.yml
```

Mac OS

```bash
cp tokyonight/night.yaml ~/Library/Application\ Support/lazygit/config.yml
```

## Config diff pager

Update `~/.gitconfig`

```yaml
[core]
  pager = delta

[interactive]
  diffFilter = delta --color-only

[delta]
  navigate = true    # use n and N to move between diff sections
  line-numbers = true

  # delta detects terminal colors automatically; set one of these to disable auto-detection
  dark = true
  # light = true

[merge]
  conflictstyle = diff3

[diff]
  colorMoved = default
```

## Copy tokyonight bat theme

```bash
mkdir -p "$(bat --config-dir)/themes"
cd "$(bat --config-dir)/themes"
# Replace _night in the lines below with _day, _night, or _storm if needed.
curl -O https://raw.githubusercontent.com/folke/tokyonight.nvim/main/extras/sublime/tokyonight_night.tmTheme
bat cache --build
bat --list-themes | grep tokyo # should output "tokyonight_night"
echo '--theme="tokyonight_night"' >> "$(bat --config-dir)/config"

```

## Apply tokyonight git theme

```bash
mkdir -p /tmp/tokyonight
cd /tmp/tokyonight
curl -O https://raw.githubusercontent.com/folke/tokyonight.nvim/main/extras/delta/tokyonight_night.gitconfig
cat /tmp/tokyonight/tokyonight_night.gitconfig >> ~/.gitconfig
```

## Apply delta theme

Linux

```bash
cp tokyonight/delta/night.yaml ~/.config/lazygit/config.yml
```

Mac OS

```bash
cp tokyonight/delta/night.yaml ~/Library/Application\ Support/lazygit/config.yml
```
