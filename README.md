# fzfmenu

A simple Shell script that spawns your terminal of choice with [fzf][].

[fzf]: https://github.com/junegunn/fzf

<img src="https://raw.githubusercontent.com/illia-shkroba/files/master/readme-fzfmenu.gif" alt="screenshot" width="800"/>

## Installation

```sh
sudo curl -o /usr/local/bin/fzfmenu https://raw.githubusercontent.com/illia-shkroba/fzfmenu/refs/heads/master/fzfmenu
sudo chmod +x /usr/local/bin/fzfmenu
```

## Dependencies

* [fzf]

## Usage

Set a `$TERMINAL` variable (you probably have it set already) or `$FZF_TERMINAL` (the latter takes
precedence). Typically, the `$TERMINAL` is set to one of these:

```sh
export TERMINAL='st'
export TERMINAL='alacritty'
export TERMINAL='kitty'
```

Using `$FZF_TERMINAL` is recommended, as it allows specifying additional options to the terminal of
choice. For example:

```sh
# Set a window class to 'my-fzf'.
export FZF_TERMINAL='st -c my-fzf'
```

When you have the `$TERMINAL` or `$FZF_TERMINAL` set, you are ready to go. Just run the script:

```sh
fzfmenu

ls -l ~/ | fzfmenu

# `fzfmenu` passes all the options to the `fzf`.
fzfmenu --color bg+:#000000 --multi
```

## How it works

The `fzfmenu` works by:

* Launching a new terminal running `fzf`.
* Forwarding any provided arguments to `fzf`.
* Redirecting standard input (*stdin*) to `fzf`.
* Capturing standard output (*stdout*) from `fzf`.
* Capturing standard error output (*stderr*) from `fzf`.

## Contribution

Pull requests and raising of potential issues are welcome.
