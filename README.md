# cmdy

A tool for managing your utility scripts. Supports subcommands.

## Examples

```
$ cmdy new foo
```

An editor is opened. You enter:

```
echo bar
```

And save it. Now you run `foo`:

```
$ foo
bar
```

`cmdy` also supports subcommands:

```
$ cmdy new foo bar baz # opens an editor for you to edit the baz script.
$ foo bar baz
baz
```

## Installation

For now, clone or download this repo and add the `cmdy` script to your path.

## Usage

#### `cmdy new <command> <subcommand> ... <script name>`

Creates a new command and subcommands.

```
$ cmdy new foo bar baz # opens an editor for you to edit the baz script.
$ foo bar baz
baz
```

#### `cmdy list`

Lists available commands.

```
$ cmdy list
baz
foo
  baz
    bar
  foo
  bar
```

#### `cmdy edit <command> <subcommand> ... <script name>`

Opens an editor for the indicated script.

```
$ cmdy new foo bar baz # opens an editor for you to edit the baz script.
```

#### `cmdy remove <command> <subcommand> ... [script name]`

Deletes a command and all its subcommands. Be careful with this one.

```
$ cmdy list
baz
foo
  baz
    bar
  foo
  bar
$ cmdy remove foo

    This will delete your command and all subcommands associated with it!
    Are you absolutely sure you want to do this?
    Enter 'yes' if you really want to do this: yes
    
    Deleted.
    
$ cmdy list
baz
```

#### `cmdy config reset`

Resets your cmdy config to the default.

#### `cmdy config get`

Prints the value of a config option.

```
$ cmdy config get color
True
```

#### `cmdy config edit`

Opens an editor to edit your config file.

#### `cmdy refresh`

Mostly used internally. Use this if you add a script manually, 
i.e., without using `cmdy new`.

#### `cmdy run`

Only used internally. Do not use.

## Todo

* Make a wheel so users can pip install cmdy.
* Add a pack command to tar.gz up all or some of the commands.
* Allow import of packs into the root namespace or prefixed.
* Support import/publish from/to github?
* Allow enabling/disabling commands through their executable bit?
