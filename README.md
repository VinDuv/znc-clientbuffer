Client specific buffers for ZNC (Debian packaging)
==================================================

The client buffer module maintains client specific buffers for
identified clients. Detailed instructions are available on [the
module's page on the ZNC wiki](http://wiki.znc.in/Clientbuffer).

This module was originally written by
[@jpnurmi](https://github.com/jpnurmi), but as [the original
repository](https://github.com/jpnurmi/znc-clientbuffer) is no longer
maintained,
[CyberShadow’s fork](https://github.com/CyberShadow/znc-clientbuffer) is a
a continuation of his work.

This fork intend to provide Debian packaging without modification.

Build
-----

Install the necessary dependencies:
```
sudo apt install debhelper-compat znc-dev
```

Then run from the source directory:
```
dpkg-buildpackage -us -uc
```

The package will be created in the parent directory. (The `-us -uc` disable
package signing; if you want a signed package, change `debian/changelog` so
the first entry contains your GPG key’s email address, and run
`dpkg-buildpackage` without options)

Pre-built packages
------------------

Pre-built packages for Debian Buster (`oldstable`) and Bullseye (`stable`) are
currently available (architecture `amd64`) on https://vinduv.github.io/debian.

Import the package signing key with:
```
curl https://vinduv.github.io/debian/packages.gpg.key | apt-key add -
```

Add the following line to `/etc/apt/sources.list` (or a separate file in
`/etc/apt/sources.list.d`):

```
deb https://vinduv.github.io/debian bullseye main
```

If you use Debian Buster, use `buster` or `oldstable` instead of `bullseye`;
on Bullseye you can also use `stable`.

you can then perform an `apt update` followed by
`apt install znc-clientbuffer`.
