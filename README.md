# irc plugin for munin

I wanted to use the `ircu` plugin for
[http://munin-monitoring.org/ Munin] but it depends on `Net::IRC` and
when you try to install it, you get warning messages.

This plugin uses `gnutls-cli` to connect to a TLS enabled IRC server.
