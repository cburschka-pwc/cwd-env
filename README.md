INSTALLATION
============

Place or link the script `cwd-env` anywhere in your `$PATH`.

USAGE
=====

Create a file named `.env` in your home directory, or the directory
where you want to run your commands, or anywhere above that directory.

Use `cwd-env <command>` to run the command.

This will execute the script in your home directory, and the first
script encountered while moving up from the local directory.
The command is then executed in the environment modified by these scripts.

EXAMPLE
=======

Contents of `.env`:

```
export PATH=`dirname ${BASH_SOURCE[0]}`/bin:$PATH
export SOMEVAR='Hello world'
```

When running `cwd-env <cmd>` in the same directory as `.env`
or any subdirectory, the script will be executed and the `$PATH`
will be locally extended.
