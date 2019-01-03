# Access GitHub via SSH

----

## [Generate a new SSH key](https://help.github.com/articles/generating-a-new-ssh-key-and-adding-it-to-the-ssh-agent/)

1. In a terminal window:

  `ssh-keygen -t rsa -b 4096 -C "me@keiranking.com"`

1. Select default file location

1. Type a secure passphrase

## [Add your SSH key to ssh-agent](https://help.github.com/articles/generating-a-new-ssh-key-and-adding-it-to-the-ssh-agent/)

1. In a terminal window:

  `eval "$(ssh-agent -s)"`

  `atom ~/.ssh/config`

1. In Atom, paste:

  ```
  Host *
  AddKeysToAgent yes
  UseKeychain yes
  IdentityFile ~/.ssh/id_rsa
  ```

1. In a terminal window:

  `ssh-add -K ~/.ssh/id_rsa`

## [Add SSH key to GitHub](https://help.github.com/articles/adding-a-new-ssh-key-to-your-github-account/)

1. In a Terminal window:

  `pbcopy < ~/.ssh/id_rsa.pub`

1. In Github, go to **Settings > SSH and GPG Keys**

1. Click **New SSH Key**

1. In the Title field, type the computer name (eg, Ukelele)

1. Paste key (copied by the `pbcopy` command) into the Key field

1. Click **Add SSH Key**
