# SSH
## Setup SSH Keys for Git
Following commands allow to use Git via SSH

    # Create new ssh key
    * ssh-keygen -t ed25519 -C "email@example.com"

    # Check if ssh-agrnt is running
    * eval "$(ssh-agent -s)"

    # Add it into ssh-agent
    * ssh-add ~/.ssh/id_ed25519

    # Test SSH connection to Github.com
    * ssh -T git@github.com

    # When connection times out then port is not allowed, in thic case use another port
    # Edit ~/.ssh/config and append the following
        Host github.com
        Hostname ssh.github.com
        Port 443

    # Save, exit and retry.
    ssh -T git@github.com
    # Should show now something like
    Hi powersnatch! You've successfully authenticated, but GitHub does not provide shell access.

Now you can clone a repository without being asked for username and password.



