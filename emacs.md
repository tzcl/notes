# Setting up Emacs

## Installing Emacs

I like using [Emacs Plus](https://github.com/d12frosted/homebrew-emacs-plus) as it comes with a brunch of extra features.

```sh
brew tap d12frosted/emacs-plus
brew install emacs-plus@30 --with-native-comp
```

## Installing Doom

```sh
git clone --depth 1 https://github.com/doomemacs/doomemacs ~/.config/emacs
~/.config/emacs/bin/doom install
```

Make sure to add `~/.config/emacs/bin` to `$PATH` to get access to Doom helpers.
