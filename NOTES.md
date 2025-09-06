# Notes

These are just rough notes as I learn or discover something.

## Macro Assembler Syntax

Comments follow a `;`.

Global labels are defined with a following `::`.

Local labels are defined with a following `:`.

`:!` seems to indicate a forced global.

`=` sets a **reassignable symbol** (i.e. variable)
`==` sets an **absolute symbol** (i.e. constant)

The `^O20000` on line 32 is octal (i.e. `8192` or `$2000`)

The `RADIX 10` on line 4 sets the default radix to 10.

`IFE` and `IFN` are conditional directives (IF Equal and IF Not equal respectively) and the general format is:

```
IFE condition,<code_to_assemble_if_true>
IFN condition,<code_to_assemble_if_false>
```

so the conditional code blocks are between angle brackets `<` `>` and can be nested (as seen in lines 36–39).

Notice the trick of something like `IFN REALIO-1` which is testing if `REALIO` equals `1` (because then `REALIO-1` would be zero/falsey).

Elsewhere `IFDIF` (IF DIFferent) is used to test for equality (for example in line 124):

```
IFDIF <value1><value2>,<code_if_different>
```

`DEFINE` defines macros.

```
DEFINE macroname,<macro_body>
DEFINE macroname (param1,param2,...),<macro_body>
```

Other directives to discuss: `TITLE`, `SEARCH`, `SALL`, `IRPC`, `REPEAT`, `IFNDEF`, `ORG`, `.XCREF`, `.CREF`, `IF1`, `IF2` `PAGE`, `COMMENT`.


## Global Labels

- `$Z` (line 6)
- `LASTWR` (line 6947)
- `TSTACK` (line 6950)


## Fun Discoveries

From lines 6934–6946, note the Copyright notice is not included on all platforms.
