# zellij devbox

This repo contains the [Devbox](https://www.jetify.com/devbox/docs/) configuration to test [zellij](https://zellij.dev/).

Devbox is used as a sandbox environment, in this case to test applications but intended for developer environments.

zellij uses a configuration file that resides in the root of the users home directory (.config/zellij/config.kdl).

Devbox has no means to manage configuration files outside the sandbox-directory.

By using the "init_hook" and the bash trap-exit mechanism it is possible to add a default configuration and remove it after exiting the devbox shell.