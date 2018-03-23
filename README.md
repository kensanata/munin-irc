# irc plugin for munin

I wanted to use the `ircu` plugin for
[Munin](http://munin-monitoring.org) but it depends on `Net::IRC` and
when you try to install that Perl module, you get warning messages. I
decided to do without a module.

This plugin uses `gnutls-cli` to connect to a TLS enabled IRC server.
