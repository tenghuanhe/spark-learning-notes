#shuffle����

shuffle������Spark����һ���ǳ���Ҫ�ĸ����Ϊstage�Ļ��ּ�����shuffleΪ���޻��ֵġ�

shuffle�������˼��ϴ�ƣ����顣

��Spark���棬���ݻ����Լ��ֲ���ԭ������Partitioner�еķ����㷨�����ģ�����HashPartitioner��RangePartitioner��

�����ķֲ�������ͨ���Զ���ĳһ�������operation�޹أ�Ϊ�˼���ĳ��operation�Ľ������Ҫ�����ݺܿ��ܲ��ں��ʵĵط���Ҳ���ǲ���ͬһ��partition�������ڶ����ͬ��patition��������ͬnode�ϡ�
Spark�ڽ��м����ʱ��һ��taskֻ���һ��partition�������㡣������ִ��reduceByKey��һ��reduce task��ʱ����һ��reduce task����Ҫ�����������е�partitions�϶����ܴ��ڣ�Ϊ�˼�����һ������reduce task��Spark��Ҫ�����е�partitions�϶�ȡ����Ҫ�����ݣ�Ȼ���ҵ�ÿһ��key��Ӧ������values��Ȼ�󽫲�ͬpartition�õ��Ľ���ϲ���һ�����õ�ÿһ��key�����ս����������reduce taskһ�㶼��ֹһ��������һ�����̾ͽ���shuffle������ÿһ��reduce task����Ҫ��������partitions�Ľ������ȡ��Щpartiton��ҪDisk IO��Memory IO�����ڴ��ڲ�ͬnode�����partition����Ҫ�����Network IO������shuffle�Ĵ��������map�ȿ���ֱ��mpipeline�Ĳ����Ƿǳ�����ġ�