# EntWatch Maker

Creates a basic EntWatch config for the current map.  
  
This will generate the number of blocks needed for all the items in a map and will fill in some info about them.  
  
Recommended to only use on test servers as the command is available for all players.  

## How to use
- Install the latest [Sourcemod](https://sm.alliedmods.net/downloads.php?branch=stable)
- Install this plugin
- Load the map you want to create a config for
- Set `ewmaker_style` to the config format your EntWatch build expects
- Use command `sm_ewmake`
- Tweak the generated values for name, color, mode, cooldown, maxuses
- Done

## Configuration
`ewmaker_path`  - a path (relative to `csgo/`) where the configs will generate  
`ewmaker_style` - style of config to generate:
- `0` = [GFL Style](https://github.com/gflclan-cs-go-ze/ZE-Configs#entwatch)
- `1` = [DarkerZ Style](https://github.com/darkerz7/CSGO-Plugins/blob/master/EntWatch_DZ/cfg/sourcemod/entwatch/maps/template.txt)
- `2` = Mapeadores MapTrack
- `3` = [EntWatch 4.2 Style](https://github.com/srcdslab/sm-plugin-entwatch-4) (`configversion 2`)

### EntWatch 4.2 style (`ewmaker_style 3`)

Generates the `"items"` / `configversion "2"` format read by [srcdslab/sm-plugin-entwatch-4](https://github.com/srcdslab/sm-plugin-entwatch-4).
For each map weapon the maker fills in `hammerid`, `allowtransfer` (0 for knives, 1 otherwise), the detected
`template` (point_template) and a `buttons` entry per detected `func_button` (`type 1` / use, `mode 0`).
`triggers` cannot be auto-detected and are written as a commented-out template to fill in by hand.
Review `name`, `short`, `color` (RRGGBB hex), and each button's `type` / `mode` / `cooldown` / `maxuses` before use.
