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

The package will be created in the parent directory.

Pre-built package
-----------------

Maybe one day…
