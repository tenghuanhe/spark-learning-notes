#Spark��һЩ���õ�lines
* ��ӡĳһ��partition�е�����Ԫ��

```
rdd.mapPartitionsWithIndex((index: Int, it: Iterator[Int]) => 
  it.toList.map(x =>
    if (index == 0)
      {println(x)})
      .iterator).collect
```
