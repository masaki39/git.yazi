# git.yazi

A [Yazi](https://github.com/sxyazi/yazi) plugin to show Git file status as linemode.

Fork of [yazi-rs/plugins:git](https://github.com/yazi-rs/plugins) with:
- Staged modifications shown in green
- Mixed staged/unstaged shown as two-color indicator

## Installation

```sh
ya pkg add masaki39/git
```

## Setup

Add to `~/.config/yazi/init.lua`:

```lua
require("git"):setup()
```

Add to `~/.config/yazi/yazi.toml`:

```toml
[[plugin.prepend_fetchers]]
id  = "git"
url = "*"
run = "git"

[[plugin.prepend_fetchers]]
id  = "git"
url = "*/"
run = "git"
```

## Status Signs

| Sign | Color | Meaning |
|------|-------|---------|
| `M` | red | Modified (unstaged) |
| `M` | green | Modified (staged) |
| `MM` | red+green | Modified (both staged and unstaged) |
| `A` | green | Added (staged) |
| `??` | red | Untracked |
| `!` | blue | Ignored |
| `D` | red | Deleted |
| `U` | yellow | Conflict |
