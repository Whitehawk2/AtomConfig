# dotfiles cofig repo

Version 0.9 :octocat:

Reorginized my dotfiles inside each dir so that it keeps
the original directory structure as expected so that it could
be directly symlinked to $HOME, or have gnu stow used.
> for stow, use the parent folder as target!

* i.e, for vim, use `stow Vim`, and not usual symlink target (`ln -sf Vim/.vim/ ~/`)

**TODO:**

* Update or deprecate atom
* Go through and update zshrc!
* vim/nvim plugins? map cleanups?

## Vim && Nvim

1. set up vundle as plugin manager:

```bash
git clone https://github.com/VundleVim/Vundle.vim.git ~/.vim/bundle/Vundle.vim
```

2. Gnu ```stow``` is "supported" - use the following inside the main dir, after cloning:

```bash
stow Vim
stow Nvim
```

this will auto symlink the sub directory into $HOME, preserving the expected tree.

3. if you already have directories set up and wish to preserve them,
or just don't want to use stow, then copy **or symlink** relevant vim/nvim files
    * vim goes to `~/.vim/`
    * nvim goes to ~/.config/nvim/

4. run `PluginInstall` in n/vim to install plugins.
    * for nvim, which i set up for k8s yaml, do:

```vim
:CocInstall coc-yaml
:CocConfig
```

and paste this into the config file:

```yaml
{
"yaml.schemas": {
      "kubernetes": "/*.yaml"
  }

}
```

   to have yaml IDE-like autocorrections, the RH Yaml language server
   **must** run in the background.
   I use docker:

```bash
docker run --rm  -it quay.io/redhat-developer/yaml-language-server:latest
```

## Atom

### NOT UPDATED

after installing Atom,
git pull and put config.cson and package.list
into ~/.atom/ **OR USE SYMLINK**

install all packages in the list

```bash
apm install --packages-file ~/.atom/package.list
```

to create a new list of packages, use

```bash
apm list --installed --bare > ~/.atom/package.list
```

### Tidying the dotfiles themselves WILL BE DONE! eventually(tm)
