# shuffle操作

shuffle操作在Spark中是一个非常重要的概念，因为stage的划分即是以shuffle为边界划分的。

shuffle字面的意思是洗牌；改组。

在Spark里面，数据划分以及分布的原则是由`Partitioner`中的分区算法决定的，比如`HashPartitioner`和`RangePartitioner`。

这样的分布由于其通用性而与某一个具体的`operation`无关，为了计算某个`operation`的结果所需要的数据很可能不在合适的地方，也就是不在同一个`partition`，而是在多个不同的`partition`，甚至不同机器节点上。

Spark在进行计算的时候，一个`task`只会对一个`partition`进行运算。例如在执行`reduceByKey`的一个`reduce task`的时候，这一个`reduce task`所需要的数据在所有的`partition`s上都可能存在，为了计算这一个单独`reduce task`，Spark需要从所有的`partition`s上读取所需要的数据，然后找到每一个`key`对应的所有`values`，然后将不同`partition`得到的结果合并到一起来得到每一个`key`的最终结果，这样的`reduce task`一般都不止一个。这样一个过程就叫做shuffle。由于每一个`reduce task`都需要来自所有`partitions`的结果，读取这些`parition`需要`Disk IO`和`Memory IO`，对于处在不同机器节点上面的`partition`还需要额外的`Network IO`，所以shuffle的代价相对于`map`等可以直接`pipeline`的操作是非常昂贵的。

能够触发shuffle的操作包括`repartition`操作比如`repartition`和`coalesce`，`Bykey`操作比如`groupByKey`和`reduceByKey`，以及`join`操作比如`cogroup`和`join`。
