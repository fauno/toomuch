# toomuch

Archives notmuch indexed emails by year and month.

It'll find all emails on inbox from a starting year and archive them
monthly up until last december.  You end up with an inbox for the
current year.

Archived email can be found under the `archive` tag plus `year-month`
tags.  Files are moved to ~/Maildir/.Archive.Year.Month/cur

## Run

See what's going to happen first:

```bash
DRYRUN=true toomuch
```

Then archive!

```bash
toomuch
```

## Options

Prepend `DRYRUN=true` to `toomuch` to see what's going to happen:

```bash
DRYRUN=true toomuch
```

Pass starting year:

```bash
toomuch 2013
```

Pass up to year-month:

```bash
toomuch 2013 2013-02
```


## TODO

* Don't hardcode email base directory
* Be flexible about the range of dates
* Modify search tags

