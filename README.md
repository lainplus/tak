# tak
### one theme script to rule them all

### features

- 270+ preloaded themes
- works on any terminal with OSC 4/11 support (most of them)
- small, posix compliant
- interactive theme selection with fzf

### why should i care

- easily switch themes inside of an open terminal not using pywal
- configure st's colors without recompiling which is cool
- scripted theme changes

### usage
put tak in your path somewhere

```
$ tak -l

3024-day
3024-night
abyss
aci
aco
......... (lists all colors)

$ tak abyss
```

or

```
$ tak -i
(interactive color select; requires fzf)
```

when you find something you like type

```
$ tak <theme name>
```

in your .bash/zsh/fish/whatever/rc

if `$TAK_HISTFILE` is set then the path it contains will be used to store recently selected themes. to load the most recently selected theme automatically you can do this:

```
export TAK_HISTFILE=~/.tak_history
[ -e "$TAK_HISTFILE" ] && tak "$(tak -l|tail -n1)"

# optional

bind -x '"\x0f":"tak $(tak -l|tail -n2|head -n1)"' #binds C-o to the previously active theme
```

in your whateverrc.


### catches

- requires a shell that properly implements OSC 4/11
- interactive mode also requires truecolor support, but the theme can still be set without it
- may cause a imperceptible flash when starting your terminal if tak is set to start off in your whateverrc
- will not help you to achieve inner peace
- may cause epilepsy in certain circumstances

