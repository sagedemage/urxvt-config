# urxvt-config
My config for the urxvt terminal emulator.

## Installation and Setup 
Install the urxvt terminal emulator
```
sudo apt install rxvt-unicode
```

Add the following to the .bashrc file, `~/.bashrc` to run tmux by default for urxvt
```
# Launch tmux if using urxvt terminal emulator
term_temp="rxvt-unicode-*"
if [[ $TERM == $term_temp ]]; then
        exec tmux && exit 0;
fi
```

Copy the Xresources file to `~/.Xresources`
```
cp -v Xresources ~/.Xresources
```

List fonts if you want to set a different font in the `~/.Xresources` file
```
fc-list | grep "Noto Mono"
```

Load Xresources file, `~/.Xresources`
```
xrdb ~/.Xresources
```

## Copy and Paste with tmux
- Copy text by highlighting text with your mouse.
- Paste text: `Ctrl+B ]`
- Switch to Copy Mode: `Ctrl+B [`

## Resources
- [Configuring URxvt to Make It Usable and Less Ugly - Addy's Blog](https://addy-dclxvi.github.io/post/configuring-urxvt/)
- [How to start urxvt with tmux - StackExchange](https://superuser.com/questions/1519805/how-to-start-urxvt-with-tmux)
- [Rebinding CTRL-ALT-C|V to CTRL-SHIFT-C|V in URxvt >= 9.20 - StackExchange](https://unix.stackexchange.com/questions/294337/rebinding-ctrl-alt-cv-to-ctrl-shift-cv-in-urxvt-9-20)
- [tmux Copy and Paste Methods With and Without the Mouse - Baeldung Linux](https://www.baeldung.com/linux/tmux-copy-paste-keyboard-mouse)
