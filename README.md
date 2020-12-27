A wrapper script to add hyperlinks to git logs
====

Install
----

You'll need a terminal supporting hyperlinks. See [Hyperlinks in terminal emulators](https://gist.github.com/egmontkob/eb114294efbcd5adb1944c9f3cb5feda) for more info.

It requires Python 3 and pygit2 to run. And the default pager is `less`.

For tmux, [a patch](https://github.com/tmux/tmux/issues/911) is needed. For less, if you set custom options (via `$LESS`), make sure `-r` (instead of `-R`) are included. If you use a custom `$PAGER`, make sure it supports hyperlinks.

git commits are linked with the `fugitive://` scheme, GitHub links are appended as `(web)`, GitHub issues are linked.
The `fugitive://` scheme is surposed to be used by the Vim plugin.
[search-and-view](https://github.com/lilydjwg/search-and-view) has a utility supporting this.

Usage
----

Method 1: Replace `git` with `git-linked` in the log viewing command (your git aliases are supported):

```sh
git-linked log ....
```

Method 2: Pipe data into `git-linked`:

```sh
git log .... --color=always | git-linked
```

Screenshot
----

![Screenshot](https://raw.githubusercontent.com/lilydjwg/git-linked/master/screenshot.png)
