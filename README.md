## fzfcache

A small cache for unique lines of text, used to speedup the load time of expensive [fzf](https://github.com/junegunn/fzf) invocations

Given any shell command as positional arguments:

- If that command had been run in the past (determined by hashing the command itself), immediately prints the cached value -- this means you can immediately select something with `fzf`
- Prints any lines from that shell command to STDOUT, which haven't already been printed from the cachefile
- Once the shell command exits, saves the shell command output to a file in `~/.cache/fzfcache/`

This keeps a history of one command, so its possible that lines from the previous result are included in the current `fzf` buffer/cachefile. So, if exact results are very important every time this is run, this probably isn't for you.

As an example:

<img src="https://raw.githubusercontent.com/seanbreckenridge/fzfcache/master/.github/demo.gif">

(If it wasn't clear, the END variable determines how many items are printed)

TODO: add real examples of me using this

### Install

Using `go install` to put it on your `$GOBIN`:

`go install github.com/seanbreckenridge/fzfcache@latest`
