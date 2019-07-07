构造题是比赛中常见的一类题型。

从形式上来看，问题的答案往往具有某种规律性，使得在问题规模迅速增大的时候，仍然有机会比较容易地得到答案。

这要求我们在解题时，要思考问题规模增长对答案的影响，这种影响是否可以推广。（比如在设计动态规划方法的时候，要考虑从一个状态到后继状态的转移会造成什么影响）。

构造题一个很显著的特点就是高自由度，也就是说一道题的构造方式可能有很多种，但是会有一种较为简单的构造方式满足题意。看起来是放宽了要求，让题目变的简单了，但很多时候，正是这种高自由度导致题目没有明确思路而无从下手。

构造题另一个特点就是形式灵活，变化多样。并不存在一个通用解法或套路可以解决所有构造题，甚至很难找出解题思路的共性。因此，下面将列举一些例题帮助读者体会构造题的一些思想内涵，给予思路上的启发。建议大家深入思考后再查看题解，也欢迎大家参与分享有趣的构造题。

## 例题：

### Example 1

#### Problem

[Vladik and fractions](http://codeforces.com/problemset/problem/743/C)

题目大意：构造一组 $x,y,z$，使得对于给定的 $n$，满足 $\dfrac{1}{x}+\dfrac{1}{y}+\dfrac{1}{z}=\dfrac{2}{n}$

#### Solution

样例二已经暴露了此题的本质~~（复读机~~

显然 $n,n+1,n(n+1)$ 为一组合法解。特殊地，当 $n=1$ 时，无解，这是因为 $n+1$ 与 $n(n+1)$ 此时相等。

至于构造思路是怎么产生的，大概就是观察样例加上一点点数感了吧。此题对于数学直觉较强的人来说并不难。

### Example 2

#### Problem

[Luogu P3599 Koishi Loves Construction](https://www.luogu.org/problemnew/show/P3599)

#### Solution

对于 task1：

当 $n$ 为奇数时，无法构造出合法解；

当 $n$ 为偶数时，可以构造一个形如 $n,1,n-2,3,\cdots$ 这样的数列。

首先，我们可以发现 $n$ 必定出现在数列的第一位，否则 $n$ 出现前后的两个前缀和必然会陷入模意义下相等的尴尬境地；

然后，我们考虑构造出整个序列的方式：

考虑通过构造前缀和序列的方式来获得原数列，可以发现前缀和序列两两之间的差在模意义下不能相等，因为前缀和序列的差分序列对应着原来的排列。

因此我们尝试以前缀和数列在模意义下为

$$
0,1,-1,2,-2,\cdots
$$

这样的形式来构造这个序列，不难发现它完美地满足所有限制条件。

对于 task2：

当 $n$ 为除 $4$ 以外的合数时，无法构造出合法解

当 $n$ 为质数或 $4$ 时，可以构造一个形如 $1,\dfrac{2}{1},\dfrac{3}{2},\cdots,\dfrac{n-1}{n-2},n$ 这样的数列

先考虑什么时候有解：

显然，当 $n$ 为合数时无解。因为对于一个合数来说，存在两个比它小的数 $p,q$ 使得 $p\times q \equiv 0 \,(mod\;n)$，如 $(3\times6)\%9=0$。那么，当 $p,q$ 均出现过后，数列的前缀积将一直为 $0$，故合数时无解。特殊地，我们可以发现 $4=2\times 2$，无满足条件的 $p,q$，因此存在合法解。

我们考虑如何构造这个数列：

和 task1 同样的思路，我们发现 $1$ 必定出现在数列的第一位，否则 $1$ 出现前后的两个前缀积必然相等；而 $n$ 必定出现在数列的最后一位，因为 $n$ 出现位置后的所有前缀积在模意义下都为 $0$。手玩几组样例以后发现，所有样例中均有一组合法解满足前缀积在模意义下为 $1,2,3,\cdots,n$，因此我们可以构造出上文所述的数列来满足这个条件。那么我们只需证明这 $n$ 个数互不相同即可。

我们发现这些数均为 $1 \cdots n-2$ 的逆元 $+1$，因此各不相同，此题得解。 

### Example 3

#### Problem

[AtCoder Grand Contest 032 B](<https://atcoder.jp/contests/agc032/tasks/agc032_b>)

#### Solution

手玩一下 $n=3,4,5$ 的情况，我们可以找到一个构造思路。

构造一个完全 $k$ 分图，保证这 $k$ 部分和相等。则每个点的 $S$  均相等，为$\dfrac{(k-1)\sum_{i=1}^{n}i}{k}$。

如果 $n$ 为偶数，那么我们可以前后两两配对，即 $\{1,n\},\{2,n-1\}\cdots$

如果 $n$ 为奇数，那么我们可以把 $n$ 单拿出来作为一组，剩余的 $n-1$ 个两两配对，即$\{n\},\{1,n-1\},\{2,n-2\}\cdots$

这样构造出的图在 $n\ge 3$ 时连通性易证，在此不加赘述。

此题得解

### Example 4

#### Problem

[BZOJ4971:[Lydsy1708月赛]记忆中的背包](<https://www.lydsy.com/JudgeOnline/problem.php?id=4971>)

#### Solution

这道题是自由度最高的构造题之一了。这就导致了没有头绪，难以入手。

首先，不难发现模数是假的。由于我们自由构造数据，我们一定可以让方案数不超过模数。

通过奇怪的方式，我们想到可以通过构造 $n$ 个 代价为 $1$ 的小物品和几个代价大于 $\dfrac{w}{2}$ 的大物品。

由于大物品只能取一件，所以每个代价为 $x$ 的大物品对方案数的贡献为 $C_{n}^{w-x}$。

令 $f_{i,j}$ 表示有 $i$ 个 $1$，方案数为 $j$ 的最小大物品数。

用 dp 预处理出 $f$ ，通过计算可知只需预处理 $i\le 20$ 的所有值即可。

此题得解