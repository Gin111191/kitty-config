# kitty-config

Kitty on macOS, made to look like [wezterm-config](https://github.com/Gin111191/wezterm-config):
Dusk-Navy when the system is dark, Everforest Light Medium when it is light, JetBrainsMono Nerd
Font Mono 13, 0.94 opacity with the desktop blurred behind, 100,000 lines of scrollback.

```sh
git clone https://github.com/Gin111191/kitty-config ~/.config/kitty
```

Needs JetBrainsMono Nerd Font installed (kitty uses its **Mono** variant). Kitty reloads the files
the moment they are saved.

| File | What it holds |
|---|---|
| `kitty.conf` | Everything; each line that is not a default says why |
| `dark-theme.conf` | Dusk-Navy, ported 1:1 from `wezterm.lua`, bright black lifted to `#93a1b3` |
| `light-theme.conf` | Everforest Light Medium, from kitty's own collection (`kitten themes`) |

| Key | Does |
|---|---|
| `CMD+OPT+↓` | Dark scheme |
| `CMD+OPT+↑` | Light scheme |

Those two keys point at `/Users/gin/.config/kitty/...` — change the path on another account.

## Not carried over from WezTerm

- **Following the system's dark/light switch** — kitty has no hook for it; hence the two keys.
- **The background gradient** — kitty cannot draw one.
- **The status strip** (folder, scheme, battery, clock).

## Images in Neovim

[nvim-config](https://github.com/Gin111191/nvim-config#images--snacksimage) draws images through
kitty. `kitty.conf` removes `TMUX` and `TERM_PROGRAM` from its shells, because a kitty started from
inside tmux would otherwise pass them on and make Neovim wrap every image for a tmux that is not
there.
