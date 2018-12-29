# Set up a Mac for product design work

----

## Coding

### Environment

1. Install:
  - github.com/thoughtbot/laptop
  - github.com/thoughtbot/dotfiles
  - Xcode

### Editor

1. Install [Atom](https://atom.io/)

1. In Atom, install these packages:
  - autoclose-html
  - busy-signal
  - erb-helper
  - escape-utils
  - intentions
  - language-liquid
  - linter
  - linter-ui-default
  - prettier-atom

### Command-line interface

1. Install [Input Mono](http://input.fontbureau.com/) typeface

1. Install [iTerm 2](https://iterm2.com/):
- Create profile and set Input Mono, 15pt as default display

1. Display folder and git locations in terminal prompt:
  - In iTerm: `atom ~/.zshrc`
  - Append to file: `export PATH="$HOME/.bin:$PATH"`

1. Get stats on git repos
  - In iTerm: `brew install git-quick-stats`
  - In iTerm, inside any repo: `git-quick-stats`

1. Set up Git aliases and user
  - In iTerm: `atom ~/.gitconfig`
  - Overwrite/add these sections:
    ```
    [alias]
      aa = add --all
      ap = add --patch
      br = branch
      branches = for-each-ref --sort=-committerdate --format=\"%(color:blue)%(authordate:relative)\t%(color:red)%(authorname)\t%(color:white)%(color:bold)%(refname:short)\" refs/remotes
      ci = commit -v
      co = checkout
      contributors = git-quick-stats
      g = git
      hist = log --graph --pretty=format:'%C(bold blue)%h%Creset  %C(yellow)%d%Creset %s %Cblue(%cr)%Creset' --abbrev-commit
      pf = push --force-with-lease
      prom = pull --rebase origin master
      rbi = rebase -i
      st = status
    ```

    ```
    [user]
    	name = Keiran King
    	email = me@keiranking.com
    ```

----

## Design

### Vector graphics and prototyping

1. Install Sketch
  - Install Craft Manager so you can upload Sketch prototypes to Invision

1. Install Figma

### Bitmap graphics

1. Install Pixelmator

### Typography

1. Install FontPlop

----

## Productivity

1. Install:
  - Wunderlist
  - 1Password
  - Alfred
  - Spectacle
  - Dropbox
  - Slack
