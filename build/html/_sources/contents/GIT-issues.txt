GIT issues
##########

1. Git auto-completion not working on Mac OSX

    * Install bash-completion

    .. code-block:: php

        brew install git bash-completion

    * You'll need to add the following to your ~/.bash_profile to get homebrew's bash-completion working:

    .. code-block:: php

        if [ -f $(brew --prefix)/etc/bash_completion ]; then
            . $(brew --prefix)/etc/bash_completion
        fi
