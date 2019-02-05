# ランダムなグラフを生成するツール

http://www.dis.uniroma1.it/challenge9/download.shtml
にあるRandgraphが最近のgccではコンパイルが通らなかったので修正したもの。

## ビルド

```
$ make
```

## 使い方

```
$ ./RandomGraph grph 20 0 1 5
```

```
Arguments:
name - name of output graph
size - size of graph (default = 20)
type - 0 - d-regular (default d = 3)
     - 1 - Gnm (default m = dn/2)
     - 2 - Gnp (default p = d/n)
     - 3 - geometric (default dist = sqrt(n))
     - 4 - random tree + d edges (default d=0)
     - 5 - string + d edges
     - 6 - binary tree + d edges
     - 7 - connected Gnm (tree + dn/2 - (n-1) edges)
     - 8 - undirected d-ary (default d=3)
     - 9 - 2D torus (p = d/100, default d=40)
     - 10 - 3D torus (p = d/100, default d=60)
     - 11 - Bullseye (d = density)
     - 12 - Hierarchical (log_d n levels, ~ (log_d n)/2 dense)
     - 13 - Grid (d=1 is square, d=2 is 16 x n/16)
dist - distribution of edge weights (default = 1)
     - 0 - unit weight edges
     - 1 - uniform in [0,1)
     - 2 - = e^R, R uniform in [0,10)
     - 3 - = e^R, R uniform in [0,25)
     - 4 - = e^R, R uniform in [0,50)
     - 5 - = e^R, R unifrom in [0,100)
     - 6 - = e^{e^R}, R uniform in [0,4)
     - 7 - = e^{e^R}, R uniform in [0,5)
     - 8 - normal dist, mean = M * .5
     - 9 - normal dist, mean = M * .2
     - 10 - normal dist, mean = M * .8
     - 11 - INTEGER uniform in [0,100000]
     - 12 - INTEGER log-uniform in [0,17]
dens - graph density (interpretation depends on type)
seed - random seed (default = current time)

  e.g., RandomGraph grph 20 0 1 5

will produce a 20 vertex, 5-regular graph named grph
whose edge weights are uniformly distributed in [0,1)
```
