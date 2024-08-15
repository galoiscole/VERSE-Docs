# Scoping

In function specifications, global variables and the function arguments are in scope.  In loop invariants, the function's local variables are also in scope.  In the `ensures` clause of a function spec, the special `return` variable is also in scope.

Conditions – specifically ownership conditions and let bindings – can introduce new variables.  Within the body of `requires`, `ensures`, and `inv`, their scoping follows the lexical structure. Moreover, variables bound in the `requires` pre-condition are in scope for loop invariants and for the `ensures` post-condition. &#x20;
