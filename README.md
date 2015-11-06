fzf is a general-purpose command-line fuzzy finder. Cygwin-fzf is the necessary code to package fzf for [Cygwin][].

For more information, see [the main fzf website][fzf].

## Usage

```sh
cygport fzf.cygport download prep install package upload
```

(Note the lack of `compile` or `test` steps; these do nothing for this repository.)

[Cygwin]: https://www.cygwin.com
[fzf]: https://github.com/junegunn/fzf
