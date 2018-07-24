# Lab 6 New script adapted 
```
<
#!/bin/sh
# Confirm the path values given below correspond to your installation

MR=/opt/cloudera/parcels/CDH/lib/hadoop-0.20-mapreduce
HADOOP=/opt/cloudera/parcels/CDH/bin

# Mark start of the loop
echo Testing loop started on `date`

# Mapper containers
for i in 4   
do
   # Reducer containers
   for j in 8 
   do                 
      # Container memory
      for k in 4096 8192
      do                         
         # Set mapper JVM heap
         echo "MAPPER CONTAINNERS: $i"
         echo "REDUCER CONTAINNERS: $i"		 
         MAP_MB=`echo "($k*0.8)/1" | bc` 
         echo "MAPPER HEAP : $MAP_MB"
         # Set reducer JVM heap 
         RED_MB=`echo "($k*0.8)/1" | bc` 
		 echo "REDUCER HEAP : $RED_MB"
        echo "STARTING TERAGEN"
        time ${HADOOP}/hadoop jar ${MR}/hadoop-examples.jar teragen \
                     -Dmapreduce.job.maps=$i \
                     -Dmapreduce.map.memory.mb=$k \
                     -Dmapreduce.map.java.opts.max.heap=$MAP_MB \
                     51200000 /results/tg-10GB-${i}-${j}-${k} 1>tera_${i}_${j}_${k}.out 2>tera_${i}_${j}_${k}.err                       

       echo "STARTING TERASORT"
	   time ${HADOOP}/hadoop jar ${MR}/hadoop-examples.jar terasort \
                     -Dmapreduce.job.maps=$i \
                     -Dmapreduce.job.reduces=$j \
                     -Dmapreduce.map.memory.mb=$k \
                     -Dmapreduce.map.java.opts.max.heap=$MAP_MB \
                     -Dmapreduce.reduce.memory.mb=$k \
                     -Dmapreduce.reduce.java.opts.max.heap=$RED_MB \
	             /results/tg-10GB-${i}-${j}-${k}  \
                     /results/ts-10GB-${i}-${j}-${k} 1>>tera_${i}_${j}_${k}.out 2>>tera_${i}_${j}_${k}.err                         

        $HADOOP/hadoop fs -rm -R -skipTrash /results/tg-10GB-${i}-${j}-${k}                         
        $HADOOP/hadoop fs -rm -R -skipTrash /results/ts-10GB-${i}-${j}-${k}        
        echo "Starting new test"		
      done
   done
done

echo Testing loop ended on `date`
>
```