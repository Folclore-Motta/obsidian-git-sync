## Definition
Pyenv is a tool to isolate the versions of python and that you have by default most of OS come with a pre installed version in UNIX systems you can check by `which python` that will return the path for the binary usually located at  `/usr/bin/python` which means that it will be available through the whole system and int the most of the cases it will not be the lasted version to make sure that system won't break.

## Application

Now imagine that we want to install a different version of the python that aren't the default that comes with the system. It will not be possible because you may break the system (Need to insert a further explanation) and not only for the python versions but for the package and libraries as well.

## PIP
The [[PIP]] is a package manager for leading with libraries in python and in most of the cases you might be aware that you can't have two package managers in your system which may cause several problems with versions and etc... (Need to insert further explanation).

And the PIP need [[Sudo]] permission to install a package because it install through the whole system `sudo pip install [package]` 

## Why not use the system package manager

By default we always look to the package manager because that the natural way of installing packages in your system but package managers tend to install their packages into the global system space instead of the user space.

## Properties

With these constraints in mind, let’s recap the criteria that would let you install and manage Python versions easily and flexibly:

- Install Python in your user space
- Install multiple versions of Python
- Specify the exact Python version you want
- Switch between the installed versions

Pyenv lets you do all of these things and more.

## Application

## Installing
To see all versions of python versions available you can type :

`pyenv install --list | grep " 3\.[678]` 

wich in that case we applied [[Regex]] to filter the result. Once you find the version that you want type:
`pyenv install -v 3.7.2`

A great way to get peace of mind that the version of Python you just installed is working properly is to run the built-in test suite:

`python -m test`

This will take a while because Pyenv is building from source because of that each version that you have installed is located nicely in your Pyenv root directory:

```
$ ls ~/.pyenv/versions/
2.7.15  3.6.8  3.8-dev
```

## Removing

All of your versions will be located at ~/.pyenv/versions This is handy because removing these versions is trivial:

`$ rm -rf ~/.pyenv/versions/2.7.15`

Of course Pyenv also provides a command to uninstall a particular Python version:

`$ pyenv uninstall 2.7.15`

## Using

Now that you’ve installed a couple of different Python versions, let’s see some basics on how to use them. First, check what versions of Python you have available:

```
$ pyenv versions
* system (set by /home/realpython/.pyenv/version)
  2.7.15
  3.6.8
  3.8-dev
```

The `*` indicates that the `system` Python version is active currently. You’ll also notice that this is set by a file in your root `pyenv` directory. This means that, by default, you are still using your system Python:

If you try to confirm this using which, you’ll see this:

```$ which python
/home/realpython/.pyenv/shims/python
```

This might be surprising, but this is how pyenv works. pyenv inserts itself into your PATH and from your OS’s perspective is the executable that is getting called. If you want to see the actual path, you can run the following:

```
$ pyenv which python
/usr/bin/python
```

If, for example, you wanted to use version 2.7.15, then you can use the global command:







