#shuffle����

shuffle������Spark����һ���ǳ���Ҫ�ĸ����Ϊstage�Ļ��ּ�����shuffleΪ���޻��ֵġ�

shuffle�������˼��ϴ�ƣ�����

��Spark���棬���ݻ����Լ��ֲ���ԭ������Partitioner�еķ����㷨�����ģ�����hash��range��

�����ķֲ�������ͨ���Զ���ĳһ�������operation�޹أ�Ϊ�˼���ĳ��operation�Ľ������Ҫ�����ݺܿ��ܲ��ں��ʵĵط���Ҳ���ǲ���ͬһ��partition�������ڶ����ͬ��patition��������ͬnode�Ĳ�ͬparition���档
Spark�ڽ��м����ʱ��һ��taskֻ���һ��partition���в�������ִ��reduceByKey��һ��reduce task��ʱ����һ��reduce task����Ҫ�����������е�partitions�϶����ܴ��ڣ�Ϊ�˼������reduce task�Ľ����Spark��Ҫ�����е�partitions�϶�ȡ����Ҫ�����ݣ�Ȼ���ҵ�ÿһ��key��Ӧ������values��Ȼ�󽫲�ͬpartition�õ��Ľ���ϲ���һ�����õ�ÿһ��key�����ս��������һ�����̾ͽ���shuffle������ÿһ��reduce task����Ҫ��������partitions�Ľ������ȡ��Щpartiton��ҪDisk IO��Memory IO�����ڴ��ڲ�ͬnode�����partition����Ҫ�����Network IO������shuffle�Ĵ�������ڿ���ֱ��pipeline�Ĳ����Ƿǳ�����ġ�
