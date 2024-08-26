# Devbox - manage application config

_Note_: This repo is only for testing [Devbox](https://www.jetify.com/devbox/docs/) with application configuration files that need to be placed in the root of the user. [zellij](https://zellij.dev/) was used as sample application, the configuration of zellij is just an example.

[Devbox](https://www.jetify.com/devbox/docs/) generates isolated, reproducible development environments using the Nix package manager.

[zellij](https://zellij.dev/) is a terminal workspace similar to `tmux` or `screen`. It uses a configuration file that resides in the root of the users home directory (`.config/zellij/config.kdl`).

Devbox has no means to manage configuration files outside the sandbox-directory.

By using the "init_hook" and the bash trap-exit mechanism it is possible to add a default configuration and remove it after exiting the Devbox shell.

## Current setup

The current setup looks for an existing configuration directory and renames it to `<config>_backup`. In the next step the application configuration is copied from the Devbox environment to the users home directory.

On `exit` (closing the Devbox environment) the previous environment is restored.

This setup "enforces" all users to use the same configuration.

## Alternative setup

The alternative setup would be to use the existing application configuration.

This setup would allow users, who are already using the application, to use their own configuration.

## Bugfix

_File not found_: Changing directories caused a "file not found" error in the initial version. This was fixed with the "PROJECT_DIR" environment variable.
