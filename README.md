# Instant Dock Reveal

Make the hidden Dock on your Mac appear the moment your pointer reaches the edge of the screen, instead of after a short delay.

<img src="demo.gif" alt="The hidden Dock appearing instantly as the pointer reaches the bottom of the screen" width="800">

This only matters if **Automatically hide and show the Dock** is turned on in **System Settings → Desktop & Dock**.

## Turn it on

Open **Terminal** (in **Applications → Utilities**), paste this line, and press Return:

```zsh
defaults write com.apple.dock autohide-delay -float 0; defaults write com.apple.dock autohide-time-modifier -float 0; killall Dock
```

## Turn it off

To bring back the normal delay, paste this line into Terminal and press Return:

```zsh
defaults delete com.apple.dock autohide-delay; defaults delete com.apple.dock autohide-time-modifier; killall Dock
```

## What the commands do

- `autohide-delay` is how long macOS waits before showing the hidden Dock. Setting it to 0 removes the wait.
- `autohide-time-modifier` sets how long the Dock takes to slide in. Setting it to 0 makes it appear at once.
- `killall Dock` restarts the Dock so the change takes effect. Your apps and windows stay open.
- `defaults delete` removes both settings, which returns them to the macOS defaults.
