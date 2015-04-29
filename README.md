# toomuch

Archives notmuch indexed emails by year and month.

It'll find all emails on inbox from a starting year and archive them
monthly up until last december.  You end up with an inbox for the
current year.

Archived email can be found under the `archive` tag plus `year-month`
tags.  Files are moved to ~/Maildir/.Archive.Year.Month/cur

It'll also phisically remove email tagged as deleted during those
months.

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

## Other

`onetoomany` can be used with postfix to deliver email and index it:

```bash
echo "you  /path/to/onetoomany" >> /etc/postfix/mailbox_commands
postmap /etc/postfix/mailbox_commands
postconf -e "mailbox_command_maps=hash:/etc/postfix/mailbox_commands"
postfix reload
```

Gotcha: if you're using `afew`, `notmuch insert` will mark your email
as seen, because of the missing unread tag during indexation.

To work around this, add this filter just before the InboxFilter in
`~/.config/afew/config`

```bash
[Filter.1]
message = Everything new is unread too
query = tag:new
tags = +unread
```


## TODO

* Don't hardcode email base directory
* Be flexible about the range of dates
* Modify search tags
* Allow to skip archiving or removal

