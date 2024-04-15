# Modprobe

Adds or removes modules from the Linux kernel, handling dependencies automatically.

## Usage

```bash
modprobe [OPTIONS]
```

## Flags

```bash
Usage:
    modprobe [options] [-i] [-b] modulename
    modprobe [options] -a [-i] [-b] modulename [modulename...]
    modprobe [options] -r [-i] modulename
    modprobe [options] -r -a [-i] modulename [modulename...]
    modprobe [options] -c
    modprobe [options] --dump-modversions filename
Management Options:
    -a, --all                   Consider every non-argument to
                                be a module name to be inserted
                                or removed (-r)
    -r, --remove                Remove modules instead of inserting
        --remove-dependencies   Also remove modules depending on it
    -R, --resolve-alias         Only lookup and print alias and exit
        --first-time            Fail if module already inserted or removed
    -i, --ignore-install        Ignore install commands
    -i, --ignore-remove         Ignore remove commands
    -b, --use-blacklist         Apply blacklist to resolved alias.
    -f, --force                 Force module insertion or removal.
                                implies --force-modversions and
                                --force-vermagic
        --force-modversion      Ignore module's version
        --force-vermagic        Ignore module's version magic

Query Options:
    -D, --show-depends          Only print module dependencies and exit
    -c, --showconfig            Print out known configuration and exit
    -c, --show-config           Same as --showconfig
        --show-modversions      Dump module symbol version and exit
        --dump-modversions      Same as --show-modversions
        --show-exports          Only print module exported symbol versions and exit

General Options:
    -n, --dry-run               Do not execute operations, just print out
    -n, --show                  Same as --dry-run
    -C, --config=FILE           Use FILE instead of default search paths
    -d, --dirname=DIR           Use DIR as filesystem root for /lib/modules
    -S, --set-version=VERSION   Use VERSION instead of `uname -r`
    -s, --syslog                print to syslog, not stderr
    -q, --quiet                 disable messages
    -v, --verbose               enables more messages
    -V, --version               show version
    -h, --help                  show this help
```

## Examples

##### Show modules that can be loaded

```bash
modprobe <tab-tab>
```

##### Show information about module

```bash
modinfo <module>
```

##### Remove module

```bash
sudo modprobe -r <module>
```

##### Install module

```bash
sudo modprobe <module>
```

## References

- [Linux.die.net](https://linux.die.net/man/8/modprobe)