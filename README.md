# tmux script manager

A small tool to manage tmux scripts. Used to add tmux aliases for running
arbitrary scripts you have created.

```
usage: update-aliases [-h] [-s LOAD_STATIC_ALIASES] [-d] [-i COMMAND_INDEX] [--dont-reset] [-w]

update tmux aliases

options:
  -h, --help            show this help message and exit
  -s LOAD_STATIC_ALIASES, --load-static-aliases LOAD_STATIC_ALIASES
                        specify a json file from which to load static aliases (default: ~/.config/tmux/conf/aliases.json)
  -d, --dry-run         print the resulting command-aliases rather than loading them
  -i COMMAND_INDEX, --command-index COMMAND_INDEX
                        specify a command-alias index to start at
  --dont-reset          do not reset the command aliases before updating
  -w, --write           write aliases to ~/.config/tmux/conf/aliases.conf
```

By default, `update-scripts` will update the aliases of the current session.
You can configure static aliases in a JSON file using a dictionary of
`"script-name": "tmux command"`. You can find an example below:

```
{
    "run-all": "command-prompt -p command \"run \\\"~/.tmux/scripts/run-all %%\\\"\"",
    "set-bg-unfocused": "set -qg status-bg colour25",
    "set-bg-focused": "set -qg status-bg default"
}
```
