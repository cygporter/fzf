fzf is a general-purpose command-line fuzzy finder. Cygwin-fzf is the necessary code to package fzf for [Cygwin][].

For more information, see [the main fzf website][fzf].

## Usage

```sh
cygport fzf.cygport download prep install package upload
```

(Note the lack of `compile` or `test` steps; these do nothing for this repository.)

Be aware there appears to be [a bug preventing the `upload` step completing](https://cygwin.com/ml/cygwin-apps/2015-11/msg00028.html), so it may be necessary to complete that manually.  Script below, assuming ssh-agent already has the requisite key loaded:

```sh
lftp -f <(
    echo "set cmd:fail-exit on"
    echo "set cmd:interactive on"
    echo "set net:max-retries 1"
    echo "open sftp://cygwin:@cygwin.com"

    for dir in x86 x86_64
    do
        echo "cd /${dir}/release"
        echo "rm -f fzf/!ready || echo -n"
        echo "mirror -v -eR fzf"
        echo "put /dev/null -o fzf/!ready"
    done
)
```


[Cygwin]: https://www.cygwin.com
[fzf]: https://github.com/junegunn/fzf
