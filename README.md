# zellij devbox

This repo contains the devbox configuration to test zellij.

devbox is used as a sandbox environment, in this case to test applications but intended for developer environments.

zellij uses a configuration file that resides in the root of the users home directory (.config/zellij/config.kdl).

devbox has no means to manage configuration files outside the devbox-directory.

By using the "init_hook" and the bash trap-exit mechanism it is possible to add a default configuration and remove it after exiting the devbox shell.