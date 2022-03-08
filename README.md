# fzf for Cygwin

fzf is a general-purpose command-line fuzzy finder. This repository contains
the necessary paraphernalia package fzf for [Cygwin][].

For more information, see [the main fzf website][fzf].


## Orphan / archive status

This repo is archived, and the fzf package on Cygwin is orphaned.

fzf was originally written in Ruby, and worked fine on Cygwin.  However, the
upstream project switched from Ruby to Go, and Go does not have a Cygwin-native
compiler.  I think there are two routes for getting updated versions of fzf on
Cygwin:

-   Start maintaining a fork of the legacy Ruby-based version of fzf, and
    package that.
-   Get a Go-based version of fzf compiled for native Windows, and package that
    along with any necessary glue to make it work with Cygwin's tty emulation /
    shells / pipe syntax / &c.

If you might want to take over, you probably want to start by looking at the
[Cygwin Package Contributor's Guide][adopt].  I'm happy to help anyone who
might want to package newer versions of fzf for Cygwin, but I don't have the
bandwidth to do significant work on either of the above approaches (or indeed
any other); you're best contacting me for that purpose via [the cygwin-apps
mailing list](https://cygwin.com/lists.html).

## Usage

```sh
cygport fzf.cygport download prep install package upload
```

(Note the lack of `compile` or `test` steps; these do nothing for this repository.)

[Cygwin]: https://www.cygwin.com
[adopt]: https://cygwin.com/packaging-contributors-guide.html#adopt
[fzf]: https://github.com/junegunn/fzf
[ml]: https://cygwin.com/lists.html
