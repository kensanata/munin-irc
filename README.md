# irc plugin for munin

I wanted to use the `ircu` plugin for
[Munin](http://munin-monitoring.org) but it depends on `Net::IRC` and
when you try to install that Perl module, you get warning messages. If
you check the
[CPAN page](http://search.cpan.org/~apeiron/Net-IRC-0.79/IRC.pm), it
says: "This module has been abandoned and is no longer developed. This
release serves only to warn current and future users about this and to
direct them to supported and actively-developed libraries for
connecting Perl to IRC."

I decided to do without the module and rewrote the plugin to use
`gnutls-cli` to connect to a TLS enabled IRC server.

If your IRC server is not TLS enabled (why!?), then you can probably
replace `gnutls-cli` with `nc` and it might still work.

Since I'm assuming your server is TLS enabled, that means certificates
are checked and that in turn means you *must* provide a hostname
as a normal certificate will most probably not work for `localhost`.

```
[irc]
env.host irc.example.org
```

Optional other config options and their defaults:

```
env.port  6697
env.cli   /usr/bin/gnutls-cli
```

You could try the following for you unencrypted IRC server:

```
env.port  6667
env.cli   /bin/nc
```
