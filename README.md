# toomuch

Archives notmuch indexed emails by year and month.

It'll find all emails on inbox from a starting year and archive them
monthly up until last december.  You end up with an inbox for the
current year.

Archived email can be found under the `archive` tag plus `year-month`
tags.  Files are moved to ~/Maildir/.Archive.Year.Month/cur

## Run

```bash
toomuch
```

## TODO

* Don't hardcode email base directory
* Be flexible about the range of dates

