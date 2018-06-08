# NAME

App::rant - generate a random text from the regex

# SYNOPSIS

    rant [OPTIONS]...

    rant
    > rEArCIba

    rant -e'\(/-_-\)/ < [x_]{20}'
    > (/-_-)/ < ____xxxx__x_xx_xxx_x

# DESCRIPTION

App::rant is a script to generate a random text from the regex.

# INSTALLATION

## With cpanm

    cpanm git://github.com/kusabashira/App-rant

## From source

    git clone git://github.com/kusabashira/App-rant
    cd App-rant
    perl Build.PL
    ./Build
    ./Build install

# OPTIONS

## -e, --expression=regex

The regex to generate a text (default: \`\\w{8}\`)

Following grammers are supported:

    \w    Alphanumeric + "_"
    \d    Digits
    \W    Printable characters other than those in \w
    \D    Printable characters other than those in \d
    .     Printable characters
    []    Character classes
    {}    Repetition
    *     Same as {0,}
    ?     Same as {0,1}
    +     Same as {1,}

### EXAMPLE

    rant -e'200'
    > 200

    rant -e'[1-9]00'
    > 600

    rant -e'[1-9][0-9]{10}'
    > 33572584712

## -c, --count=n

Print random texts n times (default: \`1\`)

### EXAMPLE

    rant -c4
    > gK1Mdux_
    > YE5ATK15
    > gFv83LLD
    > s_WCT7aj

    rant -e'[1-9]00' -c3
    > 900
    > 200
    > 700

    rant -e'[a-z]' -c9
    > L
    > S
    > O
    > 4
    > q
    > J
    > n
    > p
    > N

## -s, --separator=sep

Print sep between each text (default: \`\\n\`)

### EXAMPLE

    rant -c4 -s--
    > wUBoPdF3--zGUMASow--yHeTYKDk--ytXSjh_u

    rant -e'[ox]' -c20 -s,
    > x,x,x,o,x,x,x,o,x,x,x,x,x,x,o,x,x,o,x,o

    rant -e'"\w{10}"' -c5 -s $'\n+ '
    > "S5ofVHoA65"
    > + "AsOg6jluU9"
    > + "KcnmEInDpJ"
    > + "NM49Umwh6r"
    > + "9dG1n5tMvG"

## --help

Display usage and exit.

# LICENSE

Copyright (C) nil2.

This library is free software; you can redistribute it and/or modify
it under the same terms as Perl itself.

# AUTHOR

nil2 <nil2@nil2.org>
