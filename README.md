[![Actions Status](https://github.com/raku-community-modules/ECMA262Regex/actions/workflows/linux.yml/badge.svg)](https://github.com/raku-community-modules/ECMA262Regex/actions) [![Actions Status](https://github.com/raku-community-modules/ECMA262Regex/actions/workflows/macos.yml/badge.svg)](https://github.com/raku-community-modules/ECMA262Regex/actions) [![Actions Status](https://github.com/raku-community-modules/ECMA262Regex/actions/workflows/windows.yml/badge.svg)](https://github.com/raku-community-modules/ECMA262Regex/actions)

NAME
====

ECMA262Regex - provide support for ECMA262 regex notation

SYNOPSIS
========

```raku
use ECMA262Regex;

say ECMA262Regex.validate('\e');     # False;
say ECMA262Regex.validate('^fo+\n'); # True

# Translate regex into a Raku one (string form)
say ECMA262Regex.as-raku('^fo+\n');  # '^fo+\n'
say ECMA262Regex.as-raku('[^ab-d]'); # '<-[ab..d]>'

# Compile textual ECMA262 regex into a Raku Regex object
my $regex = ECMA262Regex.compile('^fo+\n');

say "foo\n"  ~~ $regex; # Success
say " foo\n" ~~ $regex; # Failure
```

DESCRIPTION
===========

This module parses [ECMA262 regex syntax](https://262.ecma-international.org) and can also translate it to a Raku regexes, and compile it to a `Regex` object.

AUTHORS
=======

  * Jonathan Worthington

  * Alexander Kiryuhin

Source can be located at: https://github.com/raku-community-modules/ECMA262Regex . Comments and Pull Requests are welcome.

COPYRIGHT AND LICENSE
=====================

Copyright 2018 - 2023 Edument AB

Copyright 2024 The Raku Community

This library is free software; you can redistribute it and/or modify it under the Artistic License 2.0.

