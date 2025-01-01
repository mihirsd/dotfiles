# dotfiles

Based on the [Hacker News thread](https://news.ycombinator.com/item?id=11070797) and [Atlassian tutorial](https://www.atlassian.com/git/tutorials/dotfiles)

### Get started

1. Clone into a bare repository:
```
git clone --bare git@github.com:mihirsd/dotfiles.git $HOME/.dotfiles
```

2. Define the alias in the current shell scope:
   
```
alias dotfiles='/usr/bin/git --git-dir=$HOME/.dotfiles/ --work-tree=$HOME'
```

3. Checkout the content from the bare repository to `$HOME`:

```
dotfiles checkout
```

If the command fails, backup or remove the conflicting files.

4. Set the flag `showUntrackedFiles` to `no` on this local repository:

```
dotfiles config --local status.showUntrackedFiles no
```

5. That's it! Use the `dotfiles` command to add or update dotfiles

```
dotfiles status
dotfiles add .bashrc
dotfiles commit -m "Add bashrc"
dotfiles push
```
