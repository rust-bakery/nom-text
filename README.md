# nom-text

Goal: a library that extends nom to provide better tools for text formats (programming languages, configuration files).

## current needs

Recognizing line and column in input data: [nom-locate](https://github.com/fflorent/nom_locate)

## aggregating more precise errors

Using [nom-supreme](https://github.com/Lucretiel/nom-supreme)

## error recovery

parsers need to be fault tolerant: recovering from the current error allows parsing the rest of the file: https://eyalkalderon.com/blog/nom-error-recovery/

We should also allow for various error levels (like warnings, that would not stop compilation)

## precedence

precedence rules can be annoying to write
- precedence support: https://github.com/Geal/nom/pull/1362

## bounded recursion

most language parsers end up calling themselves recursively, resulting in stack overflow issues

## nicer error diagnostic

if we have error spans, we should be able to display more context, like rustc's errors

- https://github.com/zkat/miette
- https://github.com/zesterer/ariadne
- https://github.com/brendanzab/codespan

## tokenization

should we support multiple phases, with `&str -> Vec<Token>` functions followed by `&[Token] -> AST` functions?
