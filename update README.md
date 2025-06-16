内存&分代：
-Xms4g -Xmx4g
-XX:NewRatio=3             # 新生代：老年代=1：3 
-XX:SurvivorRatio=8        # Eden:Survivor= 8:1:1 
-XX:PretenureSizeThreshold=2m   # 大对象直接进入老年代
-XX:MaxMetaspacesSize=256m   # 限制元空间大小
-Xss256k                   # 每线程栈256k，高并发场景使用

GC
-XX:+UseParallelGC         # ParallelGC 高吞吐量，计算密集型任务。批处理等
-XX:+UseG1GC               # 一般使用该配置，响应时间敏感型任务
-XX:+UseZGC                # ZGC/Shenandoah  超大堆（TB级）内存需求超100G的大型系统

-XX:MaxGCPauseMillis=200   # G1/ZGC 
-XX:G1HeapRegionSize=32m   # G1分区大小
-XX:ConcGCThreads=4:       # 并行GC线程数


