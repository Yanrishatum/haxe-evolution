# In-Function `inline var`

* Proposal: [HXP-0000](0000-in-function-inline-var.md)
* Author: [Yanrishatum](https://github.com/yanrishatum)

## Introduction

Allow creation of `inline var` inside function body.

## Motivation

Sometimes there is specific cases where you use a bunch of constant values
inside of singular function. And if this constant value may change at some point,
it requires either modifying static inline variable, non-inline variable in function
body or changing all instances of that constant in the function.

### Current workarounds
* Use `private static inline var` and access it.  
Drawbacks: Stored in static scope while it required only inside one function.
* Use simple `var` inside of body.  
Drawbacks: Not inline. May be inlined with analyzer, but there is no guarantee. Compiled allows write-access to variable.
* Usage of inline functions:
```haxe
inline function getRandomNumber():Int
{
  return 4; // chosen by fair dice roll.
            // guaranteed to be random.
}
```
Drawbacks: Long notation.
* Most probably possible with usage of macros as well.  
Drawbacks: Complexity, compilation time impact.

By allowing creation of `inline var` inside body function there will be no need in workarounding constant values inside functions.

## Detailed design

TODO
Describe the proposed design in details the way language user can understand
and compiler developer can implement. Show corner cases, provide usage examples,
describe how this solution is better than current workarounds.

## Impact on existing code

None, this introduces new usage of available syntax and in current state generating compilation error.

## Drawbacks

None.

## Alternatives

Alternatives were shown in workarounds section.
