---
layout: post
title:  "Auto-singing Python wheel packages on Mac OS X"
date:   2017-01-23 14:16:00 +0100
categories: python macosx security
---

You can automatically sign your Python wheel packages before submitting them to PyPi.

In order to do this, you will first need to install wheel:

```console
$ sudo pip install wheel
```

After that, generate a key:

```console
$ wheel keygen
```

Now, to manually sign a package, type:

```console
$ wheel sign dist/package-name-and-version.whl
```

You can also check the signature by executing:

```console
$ wheel verify dist/package-name-and-version.whl
```

You can also sign the packages automatically upon execution of `python setup.py bdist_wheel`.
In order to do this, edit your `~/.bash_profile` file and add the following line:

```bash
export WHEEL_TOOL=/usr/local/bin/wheel
```

You can then reload your configuration with `source ~/.bash_profile` and you're ready to go!