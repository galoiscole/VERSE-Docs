# Basic

## Values

| Null                                                                                                                               | `NULL`                 | `NULL`                                                                                                                                           |
| ---------------------------------------------------------------------------------------------------------------------------------- | ---------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------ |
| True                                                                                                                               | `true`                 | `true`                                                                                                                                           |
| False                                                                                                                              | `false`                | `false`                                                                                                                                          |
| Constant                                                                                                                           | `<integer><cn-type>`   | <p><code>5i32</code><br><code>5u32</code><br><code>5U</code><br><code>5UL</code><br><code>5ULL</code><br><code>5L</code><br><code>5LL</code></p> |
| <p><em><mark style="color:orange;">String literal</mark></em><br><em><mark style="color:orange;">(not implemented)</mark></em></p> | `"<string>"`           | `"foo"`                                                                                                                                          |
| Variable                                                                                                                           | `<identifier>`         | `v`                                                                                                                                              |
| Return                                                                                                                             | `return`               | `return`                                                                                                                                         |
| Parentheses                                                                                                                        | `(<expr>)`             | `(v)`                                                                                                                                            |
| Function call                                                                                                                      | `<variable>(<args>)`   | `f(v, v)`                                                                                                                                        |
| Default                                                                                                                            | `default<<base-type>>` | `default<int>`                                                                                                                                   |

### Return

The `return` keyword represents the return value of a function when used in the `ensures` clause of a function specification.

### Default

The `default<<base-type>>` keyword is replace with the default value for the indicated type.

| Type            | Default Value |
| --------------- | ------------- |
| `integer types` | `0`           |
| TODO            |               |

