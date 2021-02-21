# dotfiles cofig repo!

## Atom:

after installing Atom, 
git pull and put config.cson and package.list
into ~/.atom/ **OR USE SYMLINK**

install all packages in the list by
```bash
apm install --packages-file ~/.atom/package.list
```

to create a new list of packages, use
```bash
apm list --installed --bare > ~/.atom/package.list
```

## Vim && Nvim

1. set up vundle as plugin manager:
```bash
git clone https://github.com/VundleVim/Vundle.vim.git ~/.vim/bundle/Vundle.vim
```
2. copy **or symlink** relevant vim/nvim files 
    - vim goes to `~/.vim/`
    - nvim goes to ~/.config/nvim/

3. run `PluginInstall` in n/vim to install plugins.
    - for nvim, which i set up for k8s yaml, do:
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

### The dotfiles are not tidy yet, it on my TODO!     
