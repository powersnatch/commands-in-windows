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

## Connect to a server
If not setup in the ssh config then following command allows to connect via ssh key

    ssh -i <private key path> user@99.88.77.66

# Visual Studio
## Import Key
When you see an error like
    
    Cannot import the following key file: companyname.pfx. The key file may be password protected. 
    To correct this, try to import the certificate again or manually install the certificate to the 
    Strong Name CSP with the following key container name: VS_KEY_3E185446540E7F7A
    
Then we can import the key via 
    
    sn -i <KeyFile> <ContainerName>

# Azure CLI
## Install required module 'Az'
    # install
    Install-Module -Name Az -AllowClobber -Scope CurrentUser
    # import
    Import-Module -Name Az
When installation does not work then it can be installed via msi file too.

If it shows a warning that AzureRM cannot co-exist with installed package then this can be uninstalled via 

    # might be necessary to run as administrator
    Uninstall-AzureRm

## Commands
    # list subscriptions
    az account list

    # set to a specific subscription
    Set-AzContext -Subscription "aaa-bbb-ccc-ddd-eee"