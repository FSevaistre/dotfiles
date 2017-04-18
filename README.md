# Installation:

    git clone git://github.com/FSevaistre/dotfiles.git ~/.vim

## Tmux config

    ln -s ~/.vim/tmuxconf ~/.tmux.conf
    tmux source-file ~/.tmux.conf

### Installing plugins

  1. Add new plugin to `~/.tmux.conf` with `set -g @plugin '...'`
  2. Press `prefix` + <kbd>I</kbd> (capital I, as in **I**nstall) to fetch the plugin.

  You're good to go! The plugin was cloned to `~/.tmux/plugins/` dir and sourced.

### Uninstalling plugins

  1. Remove (or comment out) plugin from the list.
  2. Press `prefix` + <kbd>alt</kbd> + <kbd>u</kbd> (lowercase u as in **u**ninstall) to remove the plugin.

  All the plugins are installed to `~/.tmux/plugins/` so alternatively you can
  find plugin directory there and remove it.

## Vim config

### Create symlinks:

    ln -s ~/.vim/vimrc ~/.vimrc
    ln -s ~/.vim/gvimrc ~/.gvimrc

### Switch to the `~/.vim` directory, and fetch submodules:

    cd ~/.vim
    git submodule init
    git submodule update

## Bundle

### Install a new bundle:

     $ git submodule add http://github.com/tpope/vim-fugitive.git bundle/fugitive
     $ git add .
     $ git commit -m "Install Fugitive.vim bundle as a submodule."

### Update all bundles

     $ cd ..
     $ git submodule foreach git pull origin master

## To remove a submodule

  * Delete the relevant section from the .gitmodules file.
  * Delete the relevant section from .git/config.
  * Run git rm --cached path_to_submodule (no trailing slash).
  * Commit and delete the now untracked submodule files.
