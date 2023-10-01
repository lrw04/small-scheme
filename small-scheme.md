# Small Scheme

Rationale: R7RS-small Scheme is a featureful Scheme with first class environments, but could be considered too big for compiler authors.
This document specifies a smaller subset taken from R7RS-small entries, inspired by [BottomScheme](https://github.com/johnwcowan/r7rs-work/blob/master/BottomScheme.md).

Small Scheme omits libraries, datum labels, and hygienic macros.

## Lexical conventions

### Identifiers

No case-folding directives; case-sensitivity is the default.

### Datum labels

This section is removed.

## Expressions

### Primitive expression types

Everything in R7RS-small except inclusion.

### Macros

Program-defined expression types have the syntax
```
(<syntax> <datum> ...)
```
where `<syntax>` evaluates to a syntax transformer. Syntax transformers are constructed from procedures.

Its semantics are defined to be the result of `apply`ing `<syntax>` with `<datum> ...` as-is, without `<datum>`s going through evalutation.

`(syntax <transformer>)` procedure

Semantics: `Syntax` returns a version of the procedure `<transformer>` turned into a syntax transformer.

## Program structure

### Import dedlarations
### Syntax definitions
### Libraries

These sections is removed. Specifically, for the macro system in Small Scheme, syntaxes are defined in the same way as variables.

## Standard procedures

### Numbers

The supported numerical types are 64-bit signed (two's complement) integers and 64-bit (double precision) IEEE 754 floating point numbers. Big integers, complex numbers, as well as general arithmetic procedures are implemented in the standard library.

The implementation defines internal procedures for primitive actions on the primitive numerical types, and the full numerical tower.

#### Syntax of numerical constants

Case is sensitive as in symbols. The defined letters are lowercase.

### Characters
### Strings

Procedures with the suffix `-ci` are not in the standard.