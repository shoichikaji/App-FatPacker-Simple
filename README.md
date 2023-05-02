[![Actions Status](https://github.com/skaji/App-FatPacker-Simple/actions/workflows/test.yml/badge.svg)](https://github.com/skaji/App-FatPacker-Simple/actions)

# NAME

App::FatPacker::Simple - only fatpack a script

# SYNOPSIS

    $ fatpack-simple script.pl

# DESCRIPTION

App::FatPacker::Simple or its frontend `fatpack-simple` helps you
fatpack a script when **YOU** understand the whole dependencies of it.

For tutorial, please look at [App::FatPacker::Simple::Tutorial](https://metacpan.org/pod/App%3A%3AFatPacker%3A%3ASimple%3A%3ATutorial).

# MOTIVATION

App::FatPacker::Simple is an alternative for [App::FatPacker](https://metacpan.org/pod/App%3A%3AFatPacker)'s
`fatpack file` command.
Let me explain why I wrote this module.

[App::FatPacker](https://metacpan.org/pod/App%3A%3AFatPacker) brings more portability to Perl, that is totally awesome.

As far as I understand, App::FatPacker does 3 things:

- (a) trace dependencies for a script
- (b) collects dependencies to `fatlib` directory
- (c) fatpack the script with modules in `fatlib`

As for (a), I have often encountered problems. For example,
modules that I don't want to trace trace,
conversely, modules that I DO want to trace do not trace.
Moreover a core module has changed interfaces or has been bug-fixed recently,
so we have to fatpack that module with new version, etc.
So I think if you author intend to fatpack a script,
**YOU** need to understand the whole dependencies of it.

As for (b), to locate modules in a directory, why don't you use
`carton` or `cpanm`?

So the rest is (c) to fatpack a script with modules in directories,
on which App::FatPacker::Simple concentrates.

That is, App::FatPacker::Simple only fatpacks a script with features:

- automatically perl-strip modules
- has option to exclude some modules

# SEE ALSO

[App::FatPacker](https://metacpan.org/pod/App%3A%3AFatPacker)

[App::depak](https://metacpan.org/pod/App%3A%3Adepak)

[Perl::Strip](https://metacpan.org/pod/Perl%3A%3AStrip)

# COPYRIGHT AND LICENSE

Copyright 2015 Shoichi Kaji <skaji@cpan.org>

This library is free software; you can redistribute it and/or modify it under the same terms as Perl itself.
