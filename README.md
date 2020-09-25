# Steiner Systems

A [Steiner system](https://en.wikipedia.org/wiki/Steiner_system) S(t,k,v) is a collection of k-sized subsets ("blocks") of the numbers 1 to v. These collections are special because every t-sized subset of the numbers 1 to v are in exactly one block.

For example, here is a $$S(2,3,4)$$ system:
```
{1,2,3}
{1,2,4}
{1,3,4}
{2,3,4}
```

I was introduced to Steiner systems from [this review article](https://dl.acm.org/doi/10.1145/66443.66446). There is also good information on [Dan Gordon's page](https://www.dmgordon.org/steiner/).

Steiner systems follow divisibility rules: S(t,k,v) exists only if (k-i choose t-i) divides (v-i choose t-i) for all i from 0 to t-1.