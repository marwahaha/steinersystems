# Steiner Systems

A [Steiner system](https://en.wikipedia.org/wiki/Steiner_system) $$S(t,k,v)$$ is a collection of k-sized subsets ("blocks") of the numbers 1 to v. These collections are special because every t-sized subset of the numbers 1 to v are in exactly one block.

For example, here is a $$S(2,3,7)$$ system (also known as the [Fano plane](https://en.wikipedia.org/wiki/Fano_plane)):
```
{1,2,3}
{1,4,5}
{1,6,7}
{2,4,6}
{2,5,7}
{3,4,7}
{3,5,6}
```

I was introduced to Steiner systems from [this review article](https://dl.acm.org/doi/10.1145/66443.66446). There is also good information on [Dan Gordon's page](https://www.dmgordon.org/steiner/).

Some cool facts about Steiner systems:
* If you have a Steiner system $$S(t,k,v)$$, you can make a Steiner system $$S(t-1, k-1, v-1)$$ by choosing all blocks with a certain number, and deleting that number.
* Steiner systems follow divisibility rules: $$S(t,k,v)$$ only can exist if $${k-i \choose t-i}$$ divides $${v-i \choose t-i}$$ for all $$i \in \{0,\cdots,t-1\}$$.

## Table of $$S(t, t+1, v)$$

* "Trivial": There is always a "trivial" Steiner system $$S(t,k,k)$$ with one block including all numbers from 1 to k.
* "Pairs": If $$v$$ is even, then pairing all numbers from 1 to v forms a Steiner system $$S(1, 2, v)$$.

|     | $$t=1$$ | $$t=2$$ | $$t=3$$ | $$t=4$$ | $$t=5$$ | $$t=6$$ |
|:---:|:---:|:---:|:---:|:---:|:---:|:---:|
| $$v=1$$ |  -  |  -  |  -  |  -  |  -  |  -  |
| $$v=2$$ |  Trivial  |  -  |  -  |  -  |  -  |  -  |
| $$v=3$$ |  ✖  |  Trivial  |  -  |  -  |  -  |  -  |
| $$v=4$$ |  Pairs  |  ✖  |  Trivial  |  -  |  -  |  -  |
| $$v=5$$ |  ✖  |  ✖  |     |  Trivial  |  -  |  -  |
| $$v=6$$ |  Pairs  |  ✖  |     |     |  Trivial  |  -  |
| $$v=7$$ |  ✖  |  [Fano](https://en.wikipedia.org/wiki/Fano_plane)  |     |     |     |  Trivial  |
| $$v=8$$ |  Pairs  |  ✖  |     |     |     |     |
| $$v=9$$ |  ✖  |    |     |     |     |     |
| $$v=10$$|  Pairs  |  ✖  |     |     |     |     |
| $$v=11$$|  ✖  |  ✖  |     |     |     |     |
| $$v=12$$|  Pairs  |  ✖  |     |     |     |     |
| $$v=13$$|  ✖  |     |     |     |     |     |
| $$v=14$$|  Pairs  |  ✖  |     |     |     |     |
