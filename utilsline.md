#Spark中一些有用的lines
* 打印某一个partition中的所有元素

```
rdd.mapPartitionsWithIndex((index: Int, it: Iterator[Int]) => 
  it.toList.map(x =>
    if (index == 0)
      {println(x)})
      .iterator).collect
```
