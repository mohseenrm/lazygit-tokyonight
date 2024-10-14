# lazygit-tokyonight

Tokyonight theme for LazyGit

## Installation

Prerequisites:

- LazyGit
- Delta (optional)
- Bat (optional)

## Apply theme

```bash
$ cp tokyonight/moon.yaml ~/.config/lazygit/config.yml
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
# Replace _night in the lines below with _day, _moon, or _storm if needed.
curl -O https://raw.githubusercontent.com/folke/tokyonight.nvim/main/extras/sublime/tokyonight_night.tmTheme
bat cache --build
bat --list-themes | grep tokyo # should output "tokyonight_night"
echo '--theme="tokyonight_night"' >> "$(bat --config-dir)/config"

```

## Apply delta theme

```bash
cp tokyonight/delta/moon.yaml ~/.config/lazygit/config.yml
```
