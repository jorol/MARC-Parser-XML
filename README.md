# NAME

MARC::Parser::XML - Parser for MARC XML records

[![Build Status](https://travis-ci.org/jorol/MARC-Parser-XML.png)](https://travis-ci.org/jorol/MARC-Parser-XML)
[![Coverage Status](https://coveralls.io/repos/jorol/MARC-Parser-XML/badge.png?branch=devel)](https://coveralls.io/r/jorol/MARC-Parser-XML?branch=devel)
[![Kwalitee Score](http://cpants.cpanauthors.org/dist/MARC-Parser-XML.png)](http://cpants.cpanauthors.org/dist/MARC-Parser-XML)

# SYNOPSIS

    use MARC::Parser::XML;

    my $parser = MARC::Parser::XML->new( 't/marc.xml' );

    while ( my $record = $parser->next() ) { 
        # do something ...
    }

# DESCRIPTION

MARC::Parser::XML is a lightweight, fault tolerant parser for MARC XML records. Tags, indicators and subfield codes are not validated against the MARC standard. The resulting data structure is optimized for usage with the Catmandu data tool kit.

# MARC

The MARC record is parsed into an ARRAY of ARRAYs:

    $record = [
            [ 'LDR', undef, undef, '_', '00661nam  22002538a 4500' ],
            [ '001', undef, undef, '_', 'fol05865967 ' ],
            ...
            [   '245', '1', '0', 'a', 'Programming Perl /',
                'c', 'Larry Wall, Tom Christiansen & Jon Orwant.'
            ],
            ...
        ];

# METHODS

## new($file|$fh|$xml)

### Configuration

- `file`

    Path to file with MARC XML records.

- `fh`

    Open filehandle for MARC XML records.

- `xml`

    XML string.

## next()

Reads the next record from MARC input.

## \_decode($record)

Deserialize a raw MARC record to an ARRAY of ARRAYs.

# AUTHOR

Johann Rolschewski <jorol@cpan.org>

# COPYRIGHT

Copyright 2016- Johann Rolschewski

# LICENSE

This library is free software; you can redistribute it and/or modify
it under the same terms as Perl itself.

# SEE ALSO
