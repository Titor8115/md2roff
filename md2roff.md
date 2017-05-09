# md2roff 1 2017-05-09 GNU

## NAME
md2roff \- converts markdown documents to groff_man(7)

## SYNOPSIS
md2roff [*OPTION*]... [*FILE*]...

## DESCRIPTION
*md2roff* converts the input files to groff (with man package) format
and prints the result to *stdout*.

## OPTIONS

#### -h, --help
displays a short-help text and exits

#### -v, --version
displays the program version, copyright and license information and exists.

## NOTES
1. If the documents starts with `# ` then creates the TH command with this;
otherwise there will be a default TH with the file-name. Actually only the
title (name) and section are required.
```
# title section date source manual
```

2. If you write man page, use '####' for each option to automatically convert
the section to '.TP' as in GNU's manuals.

## BUGS
I suppose, a lot.

## EXAMPLE
View a markdown as console man page:
```
$ md2roff mytext.md | groff -Tutf8 -man | $PAGER
```

View a markdown as postscript man page:
```
$ md2roff mytext.md | groff -Tps -man | okular -
```

## AUTHOR
Written by Nicholas Christopoulos <nereus@freemail.gr>.

## COPYRIGHT
Copyright (C) 2017 Free Software Foundation, Inc.
.br
License GPLv3+: GNU GPL version 3 or later <http://gnu.org/licenses/gpl.html>.
.br
This is free software: you are free to change and redistribute it.
.br
There is NO WARRANTY, to the extent permitted by law.

## SEE ALSO
.BR groff_man (7),
.BR man-pages (7)