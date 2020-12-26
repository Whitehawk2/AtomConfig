# ATOM editor config

after installing Atom, 
git pull and put config.cson and package.list
into ~/.atom/

install all packages in the list by
```bash
apm install --packages-file ~/.atom/package.list
```

to create a new list of packages, use
```bash
apm list --installed --bare > ~/.atom/package.list
```
