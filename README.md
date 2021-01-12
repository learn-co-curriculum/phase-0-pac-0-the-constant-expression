# The Constant Expression

## Learning Goals

* Identify the _constant expression_
* Explain how the _constant expression_ stops evaluation

## Introduction

Lets repeat our definition of _expression_

> **Definition**: Expression: A combination of information, called _data_, and _symbols_ indicating how to combine _data_, called _operators_.

What if we were to make an expression that had no _operators_? What if it only
had _data_. For example, what if we just pass `9000` into a REPL:

<iframe height="400px" width="100%" src="https://repl.it/@MaxwellBenton2/FlatPrimaryLanservers?lite=true" scrolling="no" frameborder="no" allowtransparency="true" allowfullscreen="true" sandbox="allow-forms allow-pointer-lock allow-popups allow-same-origin allow-scripts allow-modals"></iframe>

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
`6` &mdash; a _constant expression_.

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

<table border="1" cellpadding="4" cellspacing="0">
  <tr>
    <th>Expression</th>
    <th>Has Operators?</th>
    <th>Operators</th>
    <th>Are we done?</th>
    <th>Next Step</th>
  </tr>
  
  <tr>
    <td><code>3*(10-4)</code></td>
    <td>YES</td>
    <td><code>*</code>, <code>()</code></td>
    <td>NO</td>
    <td>Zoom in on new sub-expression in <code>()</code> because of [PEMDAS][]</td>
  </tr>
  <tr>
    <td><code>(10-4)</code></td>
    <td>YES</td>
    <td><code>-</code></td>
    <td>NO</td>
    <td>Evaluate sub-expressions</td>
  </tr>
  <tr>
    <td><code>10</code></td>
    <td>NO</td>
    <td>NONE</td>
    <td>YES</td>
    <td>Zoom in on expression <code>10</code>. Constant expression! Return the value of the constant, we're done!</td>
  </tr>
  <tr>
    <td><code>4</code></td>
    <td>NO</td>
    <td>NONE</td>
    <td>YES</td>
    <td>Zoom in on expression <code>4</code>. Constant expression! Return the value of the constant, we're done!</td>
  </tr>
  <tr>
    <td><code>(10-4)</code></td>
    <td>YES</td>
    <td><code>-</code></td>
    <td>NO</td>
    <td>Replace <code>( 10 - 4 )</code> with application of <code>-</code> to <code>10</code> and <code>4</code> making <code>6</code></td>
  </tr>
  <tr>
    <td><code>3*6</code></td>
    <td>YES</td>
    <td><code>*</code></td>
    <td>NO</td>
    <td>Zoom out and replace the sub-expression with its value we just determined</td>
  </tr>
  <tr>
    <td><code>3</code></td>
    <td>NO</td>
    <td>NONE</td>
    <td>YES</td>
    <td>Zoom in on expression <code>3</code>. Constant expression! Return the value of the constant, we're done!</td>
  </tr>
  <tr>
    <td><code>6</code></td>
    <td>NO</td>
    <td>NONE</td>
    <td>YES</td>
    <td>Zoom in on expression <code>6</code>. Constant expression! Return the value of the constant, we're done!</td>
  </tr>
  <tr>
    <td><code>3*6</code></td>
    <td>YES</td>
    <td><code>*</code></td>
    <td>NO</td>
    <td>Apply <code>*</code> to <code>3</code> and <code>6</code> making <code>18</code></td>
  </tr>
  <tr>
    <td><code>18</code></td>
    <td>NO</td>
    <td>NONE</td>
    <td>YES</td>
    <td>Constant expression! Return the value of the constant, we're done!</td>
  </tr>
</table>

## Conclusion

While the _constant expression_ might seem dull, it lets us (and JavaScript)
know when expression evaluation is done _and_ establishes a groundwork for all
the following expressions. The first rule of Aristotle's logic is `A is A`; the
constant expression provides a similar "foundation" for programming.

## Resources

* [Order of Operations: PEMDAS](https://www.mathsisfun.com/operation-order-pemdas.html)

[PEMDAS]: https://en.wikipedia.org/wiki/Order_of_operations
