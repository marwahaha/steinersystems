# Steiner Systems

A [Steiner system](https://en.wikipedia.org/wiki/Steiner_system) $$S(t,k,v)$$ is a collection of k-sized subsets ("blocks") of the numbers 1 to $$v$$. These collections are special because every t-sized subset of the numbers 1 to $$v$$ are in exactly one block.

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

Here are the divisibility rules for small $$t$$ when $$k = t+1$$:

|         | Divisibility                                                 |
| :-----: | :----------------------------------------------------------- |
| $$t=1$$ | $$v \ne 1\text{ mod }2$$                                     |
| $$t=2$$ | $$v \ne 0\text{ mod }2$$ and $$v \ne 2 \text{ mod }3$$       |
| $$t=3$$ | $$v \ne 1 \text{ mod }2$$ and $$v \ne 0 \text{ mod }3$$      |
| $$t=4$$ | $$v \ne 0 \text{ mod }2$$ and $$v \ne 1 \text{ mod }3$$ and $$v \ne 4\text{ mod } 5$$ |
| $$t=5$$ | $$v \ne 1\text{ mod }2$$ and $$v \ne 2 \text{ mod }3$$ and $$v \ne 0\text{ mod } 5$$ |
| $$t=6$$ | $$v \ne 0 \text{ mod }2$$ and $$v \ne 0 \text{ mod }3$$ and $$v \ne 1\text{ mod } 5$$ and $$v \ne 6\text{ mod 7}$$ |

I've listed a table below of small values of $$t$$ and $$v$$.

* Some values of $$(t, t+1, v)$$ have no associated Steiner system:
  * ".", "..", "...", "....": No Steiner system can exist because of divisibility rules.
  * "-":  These values do not form a valid Steiner system; $$t$$ must be smaller than $$v$$.
  * "DNE": There are no Steiner systems S(4, 5, 15) or S(4, 5, 17), as [computationally verified here](https://www.sciencedirect.com/science/article/pii/S0097316508000617?via%3Dihub).
* Some values do have a Steiner system:
  * "Trivial": There is always a Steiner system $$S(t,k,k)$$ with one block including all numbers from 1 to k.
  * "Pairs": If $$v$$ is even, then pairing all numbers from 1 to v forms a Steiner system $$S(1, 2, v)$$.
  * "**✔️**": There are Steiner systems at each $$v$$ that satisfies the divisibility rules, as shown [for t=2](https://www.mscand.dk/article/view/10551/8572) and [for t=3](https://core.ac.uk/download/pdf/82538615.pdf).
  * "**M**$$_{12}$$", "**M**$$_{11}$$": The Steiner system S(5, 6, 12) corresponds to the Mathieu group **M**$$_{12}$$, which induces S(4, 5, 11) and Mathieu group **M**$$_{11}$$.
  * "**PSL$$_2$$(23)"**: There is a known Steiner system S(5, 6, 24), as described [here](https://www.ams.org/journals/mcom/1998-67-221/S0025-5718-98-00924-7/S0025-5718-98-00924-7.pdf) and [here](https://londmathsoc.onlinelibrary.wiley.com/doi/abs/10.1112/blms/8.3.263), which induces S(4, 5, 23).
  * **KNOWN**: We know of Steiner systems at S(5, 6, 36) and S(5, 6, 48), as listed [here](https://ljcr.dmgordon.org/cover/show_cover.php?v=36&k=6&t=5) and [here](https://ljcr.dmgordon.org/cover/LARGE/C_48_6_5.html).
* For the entries marked "***???***",  we simply don't know if there's a Steiner system here!

|     | $$t=1$$ | $$t=2$$ | $$t=3$$ | $$t=4$$ | $$t=5$$ | $$t=6$$ |
|:---:|:---:|:---:|:---:|:---:|:---:|:---:|
| $$v=1$$ |  -  |  -  |  -  |  -  |  -  |  -  |
| $$v=2$$ |  Trivial  |  -  |  -  |  -  |  -  |  -  |
| $$v=3$$ |  .  |  Trivial  |  -  |  -  |  -  |  -  |
| $$v=4$$ |  Pairs  |  .  |  Trivial  |  -  |  -  |  -  |
| $$v=5$$ |  .  |  ..  | . |  Trivial  |  -  |  -  |
| $$v=6$$ |  Pairs  |  .  | .. | . |  Trivial  |  -  |
| $$v=7$$ |  .  |  **✔️ ([Fano](https://en.wikipedia.org/wiki/Fano_plane))**  | . | .. | . |  Trivial  |
| $$v=8$$ |  Pairs  |  .  | **✔️** | . | .. | . |
| $$v=9$$ |  .  | **✔️** | . | ... | . | .. |
| $$v=10$$|  Pairs  |  .  | **✔️** | . | ... | . |
| $$v=11$$|  .  |  ..  | . | **M**$$_{11}$$ | . | ... |
| $$v=12$$|  Pairs  |  .  | .. | . | **M**$$_{12}$$ | . |
| $$v=13$$|  .  | **✔️** | . | .. |    .    | .... |
| $$v=14$$|  Pairs  |  .  | **✔️** | . | .. | . |
| $$v=15$$ | . | **✔️** | . | DNE | . | .. |
| $$v=16$$ | Pairs | . | **✔️** | . | DNE | . |
| $$v=17$$ | . | .. | . | DNE | . | DNE |
| $$v=18$$ | Pairs | . | .. | . | DNE | . |
| $$v=19$$ | . | **✔️** | . | .. | . | DNE |
| $$v=20$$ | Pairs | . | **✔️** | . | .. | . |
| $$v=21$$ | . | **✔️** | . | ***???*** | . | .. |
| $$v=22$$ | Pairs | . | **✔️** | . | ***???*** | . |
| $$v=23$$ | . | .. | . | **PSL$$_2$$(23)** | . | ***???*** |
| $$v=24$$ | Pairs | . | .. | . | **PSL$$_2$$(23)** | . |
| $$v=25$$ | . | **✔️** | . | .. | . | ***???*** |
| $$v=26$$ | Pairs | . | **✔️** | . | .. | . |
| $$v=27$$ | . | **✔️** | . | ***???*** | . | .. |
| $$v=28$$ | Pairs | . | **✔️** | . | ***???*** | . |
| $$v=29$$ | . | .. | . | ... | . | ***???*** |
| $$v=30$$ | Pairs | . | .. | . | ... | . |
| $$v=31$$ | . | ✔️ | . | .. | . | ... |
| $$v=32$$ | Pairs | . | **✔️** | . | .. | . |
| $$v=33$$ | . | ✔️ | . | ***???*** | . | .. |
| $$v=34$$ | Pairs | . | **✔️** | . | ***???*** | . |
| $$v=35$$ | . | .. | . | **KNOWN** | . | ***???*** |
| $$v=36$$ | Pairs | . | .. | . | **KNOWN** | . |
| $$v=37$$ | . | ✔️ | . | .. | . | ***???*** |
| $$v=38$$ | Pairs | . | **✔️** | . | .. | . |
| $$v=39$$ | . | ✔️ | . | ... | . | .. |
| $$v=40$$ | Pairs | . | **✔️** | . | ... | . |
| $$v=41$$ | . | .. | . | ***???*** | . | ... |
| $$v=42$$ | Pairs | . | .. | . | ***???*** | . |
| $$v=43$$ | . | ✔️ | . | .. | . | ***???*** |
| $$v=44$$ | Pairs | . | **✔️** | . | .. | . |
| $$v=45$$ | . | ✔️ | . | ***???*** | . | .. |
| $$v=46$$ | Pairs | . | **✔️** | . | ***???*** | . |
| $$v=47$$ | . | .. | . | **KNOWN** | . | ***???*** |
| $$v=48$$ | Pairs | . | .. | . | **KNOWN** | . |
| $$v=49$$ | . | ✔️ | . | .. | . | ***???*** |
| $$v=50$$ | Pairs | . | **✔️** | . | .. | . |
| $$v=51$$ | . | ✔️ | . | ***???*** | . | .. |
| $$v=52$$ | Pairs | . | **✔️** | . | ***???*** | . |
| $$v=53$$ | . | .. | . | ***???*** | . | ***???*** |
| $$v=54$$ | Pairs | . | .. | . | ***???*** | . |
| $$v=55$$ | . | ✔️ | . | .. | . | .... |
| $$v=56$$ | Pairs | . | **✔️** | . | .. | . |
| $$v=57$$ | . | ✔️ | . | ***???*** | . | .. |
| $$v=58$$ | Pairs | . | **✔️** | . | ***???*** | . |
| $$v=59$$ | . | .. | . | ... | . | ***???*** |
| $$v=60$$ | Pairs | . | .. | . | ... | . |
| $$v=61$$ | . | ✔️ | . | .. | . | ... |
| $$v=62$$ | Pairs | . | **✔️** | . | .. | . |
| $$v=63$$ | . | ✔️ | . | ***???*** | . | .. |
| $$v=64$$ | Pairs | . | **✔️** | . | ***???*** | . |
| $$v=65$$ | . | .. | . | ***???*** | . | ***???*** |
| $$v=66$$ | Pairs | . | .. | . | ***???*** | . |
| $$v=67$$ | . | ✔️ | . |         ..         | . | ***???*** |