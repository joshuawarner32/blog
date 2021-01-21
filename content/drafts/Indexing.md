+++
+++

# Indexing systems

There's been lots of argument on the interwebs over whether 0-based or 1-based indexing is better.

I'd like to avoid absolutes, so I'll avoid proclaiming why _you_ should use 0-based indexing. Instead I'll describe why I 0-based indexing is right _for me_.

## Background reading
* [Hisham's post](https://hisham.hm/2021/01/18/again-on-0-based-vs-1-based-indexing/), which prompted me to write this


## Points
* Simple vs Easy, Rich Hickey
    * "Easy" for me is 0-based indexing (bias based on history)
* Bias of human history (why are indices in human languages 1-based?)
* Pi vs Tau
* Index vs Offset
    * Excellent insight
    * Having two separate concepts where one works _seems_ better
    * On the other hand, there are examples where two representations are better in some manner
        * e.g. in geometric algebra, a vector vs a bi-vector in 3d are both represented by 3 scalars
        * However, the additional structure that GA imposes makes many relationships more clear
    * Seems related to 'typing'
        * In some sense an _offest_ and an _index_ are two different types
    * -> Is there a direct analogy to indexing?
* Hypothetical typed rust-ish language

```rust
struct Offset(usize);
struct Index(usize);

// overloads of Index + Offset, but not Index + Index
// maybe Offset + Offset? What would this be used for?

struct Array<T>(Vec<T>);

struct Range(Index, Offset);

// overloads of Array[Index], Array[Range]

```
