# The Constant Expression

## Learning Goals

- Identify the _constant expression_
- Explain how the _constant expression_ stops evaluation

## Introduction

Lets repeat our definition of _expression_

> **Definition**: Expression: A combination of information, called _data_, and
> _symbols_ indicating how to combine _data_, called _operators_.

What if we were to make an expression that had no _operators_? What if it only
had _data_. For example, what if we just pass `9000` into a REPL:

<iframe height="400px" width="100%" src="https://replit.com/@lizbur10/Sandbox?embed=true" scrolling="no" frameborder="no" allowtransparency="true" allowfullscreen="true" sandbox="allow-forms allow-pointer-lock allow-popups allow-same-origin allow-scripts allow-modals"></iframe>

> **Reminder**: Click the "run" button to clear any old or unwanted code in
> your code sandbox and reset the console!

In response, we get `9000`. This type of expression is known as the _constant
expression_ and it's very important, although very boring.

It's boring because it doesn't _do_ anything except be itself. But it's
important because it confirms that JavaScript knows when to stop applying
operations. It tells JavaScript to _stop_, you have an answer.

### Explain How the _Constant Expression_ Stops Evaluation

Let's consider a simple arithmetic expression. Keep in mind we apply operators
in "[PEMDAS][]" order: parenthesis, exponents, multiplication, division,
addition, subtraction.

We'll start with the expression:

![Math Expression: Step 0](https://curriculum-content.s3.amazonaws.com/phase-0/the-constant-expression/Image_54_Step0.png)

JavaScript's mission is to find a constant piece of data or a _constant
expression_. Because of `()`, it goes there first. The `(10 - 4)` is clearly
**not** a constant expression because of the `-` operator's presence. JavaScript
makes a "tree" of the two sides of the operator (`-`) and then looks on each
side to see whether those sides are _constant expressions_ i.e. "plain old
data."

![Math Expression: Step 1](https://curriculum-content.s3.amazonaws.com/phase-0/the-constant-expression/Image_54_Step1.5.png)

Since both `4` and `10` are plain old data, it can apply `-` to them and produce
`6` — a _constant expression_.

So what JavaScript now sees looks like this:

![Math Expression: Step 2](https://curriculum-content.s3.amazonaws.com/phase-0/the-constant-expression/Image_54_Step4.png)

Here again, JavaScript checks both sides of the operator `*` and, because both
sides are now _constant expressions_, applies the `*` to `3` and `6` and creates
a new _constant expression_, the answer (or "return value"):

![Math Expression: Step 3](https://curriculum-content.s3.amazonaws.com/phase-0/the-constant-expression/Image_54_Step5.png)

Whew! Fortunately, JavaScript does _all this work_ of building a tree of
operators and returning a value very quickly!

The _constant expression_ is _always_ the last expression in a complex
expression. It's how JavaScript knows it has _data_ that it can work with and
that no other operations need to be applied.

## Table Explanation

Another way of looking at this process might be to look at a table. We'll repeat
all the same things we just showed graphically, but if a table makes more sense
for you, then you'll like this one better!

This is an important strategy when learning to program: if you like thinking in
code, try out the code; if you prefer diagrams, draw a diagram; if tables make
more sense to you, build a table. An important part of learning to be a
technologist is learning to build the tools that will help you learn.

| Expression | Has Operators? | Operators | Are we done? | Next Step                                                                                      |
| ---------- | -------------- | --------- | ------------ | ---------------------------------------------------------------------------------------------- |
| `3*(10-4)` | YES            | `*`, `()` | NO           | Zoom in on new sub-expression in `()` because of PEMDAS                                        |
| `(10-4)`   | YES            | `-`       | NO           | Evaluate sub-expressions                                                                       |
| `10`       | NO             | NONE      | YES          | Zoom in on expression `10`. Constant expression! Return the value of the constant, we're done! |
| `4`        | NO             | NONE      | YES          | Zoom in on expression `4`. Constant expression! Return the value of the constant, we're done!  |
| `(10-4)`   | YES            | `-`       | NO           | Replace `( 10 - 4 )` with application of `-` to `10` and `4` making `6`                        |
| `3*6`      | YES            | `*`       | NO           | Zoom out and replace the sub-expression with its value we just determined                      |
| `3`        | NO             | NONE      | YES          | Zoom in on expression `3`. Constant expression! Return the value of the constant, we're done!  |
| `6`        | NO             | NONE      | YES          | Zoom in on expression `6`. Constant expression! Return the value of the constant, we're done!  |
| `3*6`      | YES            | `*`       | NO           | Apply `*` to `3` and `6` making `18`                                                           |
| `18`       | NO             | NONE      | YES          | Constant expression! Return the value of the constant, we're done!                             |

## Conclusion

While the _constant expression_ might seem dull, it lets us (and JavaScript)
know when expression evaluation is done _and_ establishes a groundwork for all
the following expressions. The first rule of Aristotle's logic is `A is A`; the
constant expression provides a similar "foundation" for programming.

## Resources

- [Order of Operations: PEMDAS](https://www.mathsisfun.com/operation-order-pemdas.html)

[pemdas]: https://en.wikipedia.org/wiki/Order_of_operations
