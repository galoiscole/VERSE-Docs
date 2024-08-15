# Specifications

CN specifications are written as annotations alongside C code.  Syntactically, they take the form of special comments.

{% hint style="info" %}
CN specifications are written in special C comments.

```
/*@ CN specs go here. @*/
/*@
    Or here, in multiline form.
@*/
```
{% endhint %}

Specifications can be inserted at four locations in C files.

## Function specifications

Specifications are most often placed at function definitions to describe requirements on function parameters and global variables whenever the function is called, as well as what the function ensures will be true on exit.

{% content-ref url="function-specifications.md" %}
[function-specifications.md](function-specifications.md)
{% endcontent-ref %}

## Loop invariants

Loops are notoriously difficult to verify completely automatically.  In many cases, you will need to supply a loop invariant that captures essential behavior not obvious to the solver.

{% content-ref url="loop-invariants.md" %}
[loop-invariants.md](loop-invariants.md)
{% endcontent-ref %}

## Assertions

Similar to C assertions, CN allows you to insert specification conditions at any point in the bodies of your C functions to check that what you expect to be true at that point is actually true.

{% content-ref url="assertions.md" %}
[assertions.md](assertions.md)
{% endcontent-ref %}

## Auxiliary Definitions

Just as you factor out common functionality into auxiliary C functions, it's often useful to factor out common elements of specifications.  CN lets you write auxiliary definitions at the top level in C files for use in other specs.  Auxiliary definitions can also be used to write simple data structures and algorithms that capture and verify the expected behavior of complex bits of code. This is an advanced feature.

{% content-ref url="../auxiliary-definitions.md" %}
[auxiliary-definitions.md](../auxiliary-definitions.md)
{% endcontent-ref %}
