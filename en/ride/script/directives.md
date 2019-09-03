# Directives

A **directive** is an instruction that sets the compilation mode of the [script](/ride/script.md).

``` ride
{-# DIRECTIVE_NAME VALUE #-}
```

## Directives list

| # | Directive | Directive function | Possible values |
| :--- | :--- | :--- | :--- |
| 1 | CONTENT_TYPE | Defines whether the script body is an [expression](/ride/base-concepts/expression.md) or a _set_ of [definitions](/ride/base-concepts/definition.md) | `EXPRESSION` — expression<br>`DAPP` — set of definitions |
| 2 | SCRIPT_TYPE | Defines the [script context](/ride/script/script-context.md) | `ACCOUNT`<br>`ASSET` |
| 3 | STDLIB_VERSION | Sets the version of the Standard library | `3`<br>`2`<br>`1` |
