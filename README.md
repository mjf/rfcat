The `rfcat` Tool
================
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
