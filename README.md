The `rfcat` Tool
================

Description
-----------

`rfcat` is tiny tool written almost entirely in `gawk(1)` utilizing
`nc(1)` to go over *RFC* documents online index at *IETF* website or
it's mirrors easily.

It supports *RFC* header items in searches and provides downloading
and local caching of both the *RFC* index and the *RFC* documents
in the `$HOME/.rfcat` folder (that must be created manualy before
first run of the `rfcat` tool).

Once *IETF* moved their *RFC* archive on *HTTPS* only the `rfcat`
lost it's ability to connect to the website using just `gawk(1)`'s
network socket functionality.  Therefor `rfcat` now spawns `nc(1)`
for online access to the *IETF* archive.

Usage Hints
-----------

`vim(1)` is excellent text editor but can be used as a pager too
with some minor effort.  Put this to your `$HOME/.bash_aliases`:

```sh
# use vim(1) as pager
alias pg='vim -R +'\''set nowrap'\'' +'\''map <Space> <PageDown>'\'' +'\''map q :quit<CR>'\'''

# use rfcat with `pg` alias
alias rfc='(read rfc && rfcat $rfc | pg -)<<<'
```

Now call `rfcat` via the defined alias:

```sh
> rfc 1234
```

Of course it's supposed that you have already syntax highlighting
rulesets for *RFC* documents in place.
