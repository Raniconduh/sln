# sln

A symlink manager especially for linking binary programs to a single point. Similar to Debian's `update-alternatives` but simpler.

## Usage

```
sln [FLAG] [OPTION] [ARG]...

Options:
  add GROUP LINK PATH      Create a link in GROUP with name LINK to path PATH
  del GROUP LINNK          Delete group GROUP's link of name LINK
  group GROUP              Create group with name GROUP
  list [GROUP]             List all groups or list links in GROUP if specified
  set GROUP LINK           Set the default link of GROUP to LINK
  ungroup GROUP            Remove GROUP entirely (and its links)
  unset GROUP              Unset the default link of GROUP

Flags:
  --path=PATH              Change the sln path from '/usr/local/bin' to PATH
  --dbdir=PATH             Change the sln database directory from '/usr/local/share/sln' to PATH

Example:
To create a new group titled "lua" with a link titled "lua53"
which links to the path of the "lua53" executable:
  $ sln group lua
  $ sln add lua lua53 $(which lua53)
  $ sln set lua lua53
```

To permanently change the database or binary installation locations, edit the script and change `d_path` for the database, and `b_path` for the binary installation path.

## Installing

Simply run `install -m755 sln /usr/local/bin/sln` or to any other place in your `$PATH`. From there it is callable as `sln`.
