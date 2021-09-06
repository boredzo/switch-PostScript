# switch-case library for PostScript

## What does this do?

This is an implementation of a `switch` operator for PostScript programs that replicates the `switch...case` syntax seen in many other programming languages, such as C.

The `switch...case` construct (which goes by a variety of names) generally has the following elements:

- The switch is entered with a singular value, here called the comparand, to be compared to other values. (In C, the value must be an integer, but other languages may allow comparing values of any type.)
- The switch contains zero or more cases, each corresponding to a value, and will execute one or more code branches depending on the value chosen. (Some languages restrict the switch to executing exactly one code branch; C bases it on `goto`-like labels, and consequently has a "fall-through" mechanic where execution continues past subsequent labels if not explicitly broken with a `break` statement.)
- The switch may have a "default" case containing code to be executed if no other case matches.

This implementation has the following elements:

- The comparand can be of any type except `arraytype`. This means arrays and procs cannot be used as comparands.
- The switch will execute exactly one of the supplied procs unless no case value matches the comparand and no default was supplied.
- A default case may be supplied using a value of `null`.