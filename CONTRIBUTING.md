# Contributing to `nvim-web-devicons`

Thank you for your contribution!

## Name

Please name your commits and the PR simply e.g.

    add .tex
    update makefile icon
    update .kt colors

## Generate Colors

Add or update icons in `scripts/nvim-web-devicons.lua`.

There are two tables where icons can be added:
1. icons_by_filename
2. icons_by_file_extension

Add the icon in table 1. if the icon is for a file that is always named that
way, for example `.gitconfig`. Add to table 2. if the icon is for all files
with an extension.

Each icon must have the following (this is an example):
```lua
[".gitconfig"] = {
    icon = "",
    color = "#41535b",
    cterm_color = "0",
    name = "GitConfig",
},
```
___Key/value pairs must appear in the same exact order!___

- `color` must contain a color in the html notation
- `cterm_color` must be below `color`, and it must contain a number (any number)
- the correct value for `cterm_color` will be generated by the script

Add [vim-colortemplate](https://github.com/lifepillar/vim-colortemplate) to &runtimepath. The easiest way to do this is via your package manager.

Ensure your current working directory is the repo root.
Run `make`. This will:
- Update `cterm_color` based on `color`
- Generate `nvim-web-devicons-light.lua`

Please commit both `nvim-web-devicons.lua` and `nvim-web-devicons-light.lua`

## Styling And Format

TODO @alex-courtis

## Pull Request

Please reference any issues in the description e.g. "resolves #1234".

Please check "allow edits by maintainers" to allow nvim-web-devicons maintainers to make small changes such as documentation tweaks.

## Documentation

When modifying or adding API, please update [Usage](README.md#Usage)
