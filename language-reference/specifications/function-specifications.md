# Function Specifications

Function specifications define a contract for your C functions, capturing assumptions about input parameters and the state of global variables when the function is called as well as the effects the caller should expect on function exit.

Function specs are placed between the function header and body.

```
int f(int *p)
/@*
    // Function spec goes here.
*@/
{
    return *p;
}
```

Function statements can have the following clauses.

| <p><code>requires</code><br>  <code>&#x3C;condition>;</code><br>  <code>&#x3C;condition>;</code></p> | One or more conditions the function assumes are true when called.                                                                |
| ---------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------- |
| <p><code>ensures</code><br>  <code>&#x3C;condition>;</code><br>  <code>&#x3C;condition>;</code></p>  | One or more conditions the function ensures are true on exit.                                                                    |
| `accesses <id1>; <id2>;`                                                                             | Global variables the function uses.                                                                                              |
| `trusted;`                                                                                           | A special keyword telling CN _not_ to verify the function but instead to assume the specification is correct.  Use with caution. |
| `function <id>;`                                                                                     | Experimental feature.  Automatically derives a CN function (see Auxiliary Definitions) from the C function.                      |

## Requires and Ensures

These are the bread-and-butter clauses of function specifications.  Together, they define a formal contract that callers of your function can rely on.

These clauses contain lists of [conditions.md](../conditions.md "mention").  Here's an example.

```
int f(int *p)
/*@
  requires
    // p is not NULL and can be read and written by this function.
    Owned(p);

  ensures
    // Ownership of p is returned to the caller.  p remains non-NULL
    // and can be read and written by the caller. 
    take v = Owned(p);

    // The value returned by this function is equal to the contents of p.
    return == v;
*@/
{
    return *p;
}
```

## Accesses

The `accesses` clause is syntactic sugar for requiring ownership of global variables and ensuring the return of that ownership.

In other words, the following function specifications are equivalent.

```
int glob = 0;

int f1()
/*@
  accesses glob;
@*/
{
    return glob;
}

int f2()
/*@
  requires
    take glob_in = Owned<int>(&glob);

  ensures
    take glob_out = Owned<int>(&glob);
*@/
{
    return glob;
}
```

## Trusted Functions

The `trusted` keyword tells CN to assume that the function satisfies its specification, rather than trying to verify it.  This is useful for defining the expected behavior of library functions when you don't have the source code.  And sometimes convincing the solver of the truth of your specification takes more time than you currently have.

The `trusted` keyword is also dangerous, because your function may, in fact, _not_ implement its spec.  CN will verify every function that calls it assuming that the conditions it claims to ensure will hold, but that may not be the case when you run your program, leading to bugs or security vulnerabilities.

{% hint style="warning" %}
TODO: Explain how to use runtime specification testing to validate trusted specs.
{% endhint %}

Here are a few examples of how to use (and not use) the `trusted` keyword.

```
// TODO: how to write trusted specs for library functions.
int library_function(*p);

// Bad – the function does not match the spec. 
int whoops(int *p)
/*@
  trusted;

  requires
    take p_in = Owned(p);

  ensures
    take p_out = Owned(p);
    return == p_out;
*@/
{
    int x = *p;
    free(p);
    return x + 1;
}
```
