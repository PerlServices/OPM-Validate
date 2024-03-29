[![Kwalitee status](https://cpants.cpanauthors.org/dist/OPM-Validate.png)](https://cpants.cpanauthors.org/dist/OPM-Validate)
[![GitHub issues](https://img.shields.io/github/issues/perlservices/OPM-Validate.svg)](https://github.com/perlservices/OPM-Validate/issues)
[![CPAN Cover Status](https://cpancoverbadge.perl-services.de/OPM-Validate-1.13)](https://cpancoverbadge.perl-services.de/OPM-Validate-1.13)
[![Cpan license](https://img.shields.io/cpan/l/OPM-Validate.svg)](https://metacpan.org/release/OPM-Validate)

# NAME

OPM::Validate - Validate .opm files

# VERSION

version 1.13

# SYNOPSIS

```perl
use v5.20;
use OPM::Validate;

my $content = 'content of .opm file';
my $success = eval {
    OPM::Validate->validate( $content );
};

say "It's valid" if $success;
```

# DESCRIPTION

_.opm_ files are used as addons for the [Znuny](https://znuny.org), [OTOBO](https://otobo.de) and
((OTRS)) Community Edition ticketing systems. They are XML files with specific XML tags.

This module checks if all needed XML tags are there.

Currently the error messages might be misleading, this is something we are working on.

# METHODS

## validate

This checks the given string if it matches the needs. It `die`s if an error occurs and returns `1` otherwise.

```perl
use v5.10;
use OPM::Validate;

my $content = 'content of .opm file';
my $success = eval {
    OPM::Validate->validate( $content );
};

say "It's valid" if $success;
```



# Development

The distribution is contained in a Git repository, so simply clone the
repository

```
$ git clone git://github.com/perlservices/OPM-Validate.git
```

and change into the newly-created directory.

```
$ cd OPM-Validate
```

The project uses [`Dist::Zilla`](https://metacpan.org/pod/Dist::Zilla) to
build the distribution, hence this will need to be installed before
continuing:

```
$ cpanm Dist::Zilla
```

To install the required prequisite packages, run the following set of
commands:

```
$ dzil authordeps --missing | cpanm
$ dzil listdeps --author --missing | cpanm
```

The distribution can be tested like so:

```
$ dzil test
```

To run the full set of tests (including author and release-process tests),
add the `--author` and `--release` options:

```
$ dzil test --author --release
```

# AUTHOR

Perl-Services.de <info@perl-services.de>

# COPYRIGHT AND LICENSE

This software is copyright (c) 2021 by Perl-Services.de.

This is free software; you can redistribute it and/or modify it under
the same terms as the Perl 5 programming language system itself.
