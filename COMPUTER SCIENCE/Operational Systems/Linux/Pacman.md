
# Removing the lock 

When _pacman_ is about to alter the package database, for example installing a package, it creates a lock file at `/var/lib/pacman/db.lck`. This prevents another instance of _pacman_ from trying to alter the package database at the same time.

If _pacman_ is interrupted while changing the database, this stale lock file can remain. If you are certain that no instances of _pacman_ are running

```shell
$ pgrep -u root -l pacman
```

then delete the lock file:

```shell
$ rm /var/lib/pacman/db.lck`
```

## Cleaning the package cache

Pacman stores its downloaded packages in `/var/cache/pacman/pkg/` and does not remove the old or uninstalled versions automatically. This has some advantages:

* It allows to downgrade a package without the need to retrieve the previous version through other means, such as the Arch Linux Archive.
* A package that has been uninstalled can easily be reinstalled directly from the cache directory, not requiring a new download from the repository.

However, it is necessary to deliberately clean up the cache periodically to prevent the directory to grow indefinitely in size.

The [paccache(8)](https://man.archlinux.org/man/paccache.8) script, provided within the [pacman-contrib](https://aur.archlinux.org/packages/pacman-cleanup-hook) package, deletes all cached versions of installed and uninstalled packages, except for the most recent three, by default:

```shell 
 $ paccache -r
```

You cna enable and start **paccache.timer** to discard unused packages weekly.

Tip: You can create a hook to run this automatically after every pacman transaction, install [pacman-cleanup-hook](https://aur.archlinux.org/packages/pacman-cleanup-hook) and see other examples of hooks [hooks](https://man.archlinux.org/man/alpm-hooks.5)

```
[Trigger]
Type = Package
Operation = Remove
Operation = Install
Operation = Upgrade
Target = *

[Action]
Description = Removing unnecessary cached files (keeping the latest two)...
When = PostTransaction
Exec = /usr/bin/paccache -rvk2
```

Create the file with the name that you want with the .hook extension `name.hook`  and save in `/etc/pacman.d/hooks` if the directory doesn't  exist create one or you can also change in the config file

You can also define how many recent versions you want to keep. To retain only one past version use:

```shell
$ paccache -rk1
```

Add the -u/--uninstalled switch to limit the action of paccache to uninstalled packages. For example to remove all cached versions of uninstalled packages, use the following:

```shell
$ paccache -ruk0
```

# Mirrors

## Force pacman to refresh the package lists

Mirrors can be out of sync and the package list from the old mirror may not correspond to the package list of the new mirror, even though the dates of the lists may suggest that they do.

After creating/editing /etc/pacman.d/mirrorlist, issue the following command:

```shell
$ pacman -Syyu
```
Passing two --refresh/-y flags forces pacman to refresh all package lists even if they are considered to be up to date. 