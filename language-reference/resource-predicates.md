# Resource Predicates

Resource predicates have _inputs_ and _outputs_.  Roughly speaking, inputs specify _what is owned_, and outputs are information that can be derived from the ownership, such as the value a pointer points to.

| Owned | <p><code>Owned(&#x3C;expr>)</code><br><code>Owned&#x3C;ctype>(&#x3C;expr>)</code></p> | <p><code>Owned(p + 1i32)</code><br><code>Owned&#x3C;int>(p + 1i32)</code></p> |
| ----- | ------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------- |
| Block | <p><code>Block(&#x3C;expr>)</code><br><code>Block&#x3C;ctype>(&#x3C;expr>)</code></p> | <p><code>Block(p + 1i32)</code><br><code>Block&#x3C;int>(p + 1i32)</code></p> |

## Owned

`Owned<T>` takes as input a pointer-expression. For a given pointer expression `P`, `Owned<T>(P)` asserts full (read and write) ownership of memory at address `P`, at C-type `T`. Its output is the memory value at address `P`. `Owned<T>(P)` allows reading and writing `P`, or any of its parts.

## Block

`Block<T>` takes as input a pointer-expression. For a given pointer expression `P`, `Block<T>(P)` asserts ownership of memory at address `P`, at C-type `T`; unlike `Owned`, `Block` represents “uninitialized” memory, which can be written but not read. The output of `Block` is `void`.

## Custom Resource Predicates

For complex structures, CN lets you define custom resource predicates to establish ownership and extract a logical representation of the object.  For example, you might define a custom predicate to traverse a linked list, establish ownership of each node, and return a logical array of values.

See [custom-resource-predicates.md](auxiliary-definitions/custom-resource-predicates.md "mention") for more details.
