vim-setup
===============

Personal configuration of the editor I came using Pathogen, support the languages:

* Scala

These settings are based on:

* https://github.com/tlazaro/vim-scala-setup
* http://vimcasts.org/episodes/synchronizing-plugins-with-git-submodules-and-pathogen/

Install guide
=============

To install just download the repository, and have ``git`` installed and ``vim`` version 8 or greater.

UNIX
----

Basically clone the repository to your ``.vim`` folder, make your .vimrc a link to the one inside the cloned repository and then download all the submodules (the plugins).

    git clone https://github.com/ecorbari/vim-setup.git ~/.vim
    ln -s ~/.vim/vimrc ~/.vimrc
    cd ~/.vim
    git submodule update --init
    

Final Setup Steps
------------------

  * Compile ``command-t``: https://github.com/wincent/Command-T
  * Install ``ctags`` in your OS 
  * Install `powerline`

### Install Powerline Linux

Instal powerline from the bundle in `.vim`:

    pip install --user --editable=~/.vim/bundle/powerline

    cp ~/.vim/bundle/powerline/font/PowerlineSymbols.otf ~/.fonts/
    fc-cache -vf ~/.fonts/

    mkdir -p ~/.config/fontconfig/conf.d/
    cp ~/.vim/bundle/powerline/font/10-powerline-symbols.conf ~/.config/fontconfig/conf.d/

Install fonts that work with Powerline:

    git clone https://github.com/powerline/fonts.git
    cd fonts
    ./install.sh
    

Then set you terminal to use one of those font, you can try `Inconsolata for Powerline`.

Updating plugins
================

To update the code of every plugin:

    git submodule foreach git pull origin master
    
If a new submodule (plugin) is added to this repository since the time you cloned it you must:

    git submodule update --init


Add or remove plugins
================
    
* Example to add new plugin:

    cd ~/.vim 
    git submodule add https://github.com/wincent/command-t.git bundle/command-t
    git submodule init

* Example to remove plugin:

    cd ~/.vim 
    git submodule deinit bundle/vim-rvm
    git rm bundle/vim-rvm
    git rm --cached bundle/vim-rvm
    rm -rf .git/modules/bundle/vim-rvm

Collaboration
=============

Please contact me for any problem, suggestion or enhancements, preferably by reporting an issue through GitHub. Pull requests more than welcome!
