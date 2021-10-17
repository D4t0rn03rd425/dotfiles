# dotfiles

these are my dotfiles, tracked with a bare git repository as described [here](https://www.atlassian.com/git/tutorials/dotfiles)

## initialize a bare git repository
- `git init --bare $HOME/.dotfiles` init a bare git repository in your home directory
- `alias config='/usr/bin/git --git-dir=$HOME/.dotfiles/ --work-tree=$HOME'` create an alias to track dotfiles
- `config config --local status.showUntrackedFiles no`
- `echo "alias config='/usr/bin/git --git-dir=$HOME/.dotfiles/ --work-tree=$HOME'" >> $HOME/.bashrc`
- `echo ".dotfiles" >> .gitignore` the source repository has to ignore the folders where you'll clone it

## install dotfiles onto a new system
- `alias config='/usr/bin/git --git-dir=$HOME/.dotfiles/ --work-tree=$HOME'` create an alias to track dotfiles
- `git clone --bare <git-repo-url> $HOME/.dotfiles` clone the dotfiles into a bare repository
- `alias config='/usr/bin/git --git-dir=$HOME/.dotfiles/ --work-tree=$HOME'` define the alias in the current shell scope
- `config checkout`
- `config config --local status.showUntrackedFiles no`
