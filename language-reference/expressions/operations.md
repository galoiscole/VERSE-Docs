# Operations

## Arithmetic Operations

<table data-header-hidden><thead><tr><th width="190"></th><th>Syntax</th><th>Examples</th></tr></thead><tbody><tr><td>Addition</td><td><code>&#x3C;expr> + &#x3C;expr></code></td><td><code>2 + 2</code><br><code>ptr + 1</code></td></tr><tr><td>Subtraction</td><td><code>&#x3C;expr> - &#x3C;expr></code></td><td><code>2 - 1</code><br><code>ptr - 1</code></td></tr><tr><td>Negation</td><td><code>-&#x3C;expr></code></td><td><code>-1</code></td></tr><tr><td>Multiplication</td><td><code>&#x3C;expr> * &#x3C;expr></code></td><td><code>1 * 2</code></td></tr><tr><td>Division</td><td><code>&#x3C;expr> / &#x3C;expr></code></td><td><code>1 / 2</code></td></tr><tr><td>Modulus</td><td><code>&#x3C;expr> % &#x3C;expr></code></td><td><code>1 % 2</code></td></tr><tr><td><em><mark style="color:orange;">Exponentiation (not implemented)</mark></em></td><td><code>pow(&#x3C;expr>, &#x3C;expr>)</code></td><td><code>pow(2, 2)</code></td></tr></tbody></table>

## Binary (Bitwise) Operations

| And                                                                                                                             | `<expr> & <expr>`  | `1 & 2`  |
| ------------------------------------------------------------------------------------------------------------------------------- | ------------------ | -------- |
| <p><em><mark style="color:orange;">Or</mark></em><br><em><mark style="color:orange;">(not implemented)</mark></em></p>          | `<expr> \| <expr>` | `1 \| 2` |
| Not                                                                                                                             | `~<expr>`          | `~1`     |
| <p><em><mark style="color:orange;">Shift left</mark></em><br><em><mark style="color:orange;">(not implemented)</mark></em></p>  | `<expr> << <expr>` | `1 << 2` |
| <p><em><mark style="color:orange;">Shift right</mark></em><br><em><mark style="color:orange;">(not implemented)</mark></em></p> | `<expr> >> <expr>` | `1 >> 2` |

## Boolean Operations

| Conjunction | `<expr> && <expr>`      | `true && false`      |
| ----------- | ----------------------- | -------------------- |
| Disjunction | `<expr> \|\| <expr>`    | `true \|\| false`    |
| Negation    | `!<expr>`               | `!true`              |
| Implication | `<expr> implies <expr>` | `false implies true` |

## Built-in Operations

<table data-header-hidden><thead><tr><th width="250"></th><th></th><th></th></tr></thead><tbody><tr><td>Good</td><td><code>good&#x3C;ctype>(&#x3C;expr>)</code></td><td>TODO</td></tr><tr><td>Location</td><td><code>{&#x3C;expr>}@&#x3C;name></code></td><td>TODO</td></tr><tr><td>Size of</td><td><code>sizeof&#x3C;ctype></code></td><td><code>sizeof&#x3C;int></code></td></tr><tr><td>Unchanged</td><td><code>{&#x3C;expr>} unchanged</code></td><td><code>{ptr} unchanged</code></td></tr></tbody></table>

## Pointer Operations

| Dereference | `*<expr>` | `*ptr` |
| ----------- | --------- | ------ |
| Address of  | `&<expr>` | `&v`   |

## Relational Operations

| Equal                    | `<expr> == <expr>` | `true == false` |
| ------------------------ | ------------------ | --------------- |
| Not equal                | `<expr> != <expr>` | `true != false` |
| Less than                | `<expr> < <expr>`  | `1 < 2`         |
| Greater than             | `<expr> > <expr>`  | `1 > 2`         |
| Less than or equal to    | `<expr> <= <expr>` | `1 <= 2`        |
| Greater than or equal to | `<expr> >= <expr>` | `1 >= 2`        |
