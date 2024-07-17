# EFREI Paris, 2021 Big Data Introduction 2021 YARN & MapReduce 2

## 1.8 Remarkable trees of Paris
You are going to write some MapReduce jobs on the remarkable trees of Paris using this dataset. Download the file and put it in your HDFS home directory. Remember to ignore the first row in every mapper on this dataset.

`
[thomas.almeida@bigdata01 ~]$ hdfs dfs -rm -r /user/thomas.almeida/output_districts
yarn jar /home/thomas.almeida/hadoop-examples-mapreduce-1.0-SNAPSHOT-jar-with-dependencies.jar district /user/thomas.almeida/trees.csv /user/thomas.almeida/output_districts
hdfs dfs -cat /user/thomas.almeida/output_districts/part-00000
24/07/15 11:39:08 INFO fs.TrashPolicyDefault: Moved: 'hdfs://efrei/user/
thomas.almeida/output_districts' to trash at: hdfs://efrei/user/thomas.almeida/.Trash/Current/user/thomas.almeida/output_districts1721036348626 
24/07/15 11:39:13 INFO client.AHSProxy: Connecting to Application History server at bigdata02.efrei.hadoop.clemlab.io/62.210.145.80:10200       
24/07/15 11:39:13 INFO hdfs.DFSClient: Created token for thomas.almeida:
 HDFS_DELEGATION_TOKEN owner=thomas.almeida@EFREI.HADOOP.CLEMLAB.IO, ren
ewer=yarn, realUser=, issueDate=1721036353617, maxDate=1721641153617, sequenceNumber=1635, masterKeyId=22 on ha-hdfs:efrei
24/07/15 11:39:13 INFO kms.KMSClientProvider: New token created: (Kind: 
kms-dt, Service: kms://http@bigdata03.efrei.hadoop.clemlab.io:9292/kms, 
Ident: (kms-dt owner=thomas.almeida, renewer=yarn, realUser=, issueDate=
1721036353675, maxDate=1721641153675, sequenceNumber=1521, masterKeyId=8))
24/07/15 11:39:13 INFO security.TokenCache: Got dt for hdfs://efrei; Kin
d: HDFS_DELEGATION_TOKEN, Service: ha-hdfs:efrei, Ident: (token for thom
as.almeida: HDFS_DELEGATION_TOKEN owner=thomas.almeida@EFREI.HADOOP.CLEM
LAB.IO, renewer=yarn, realUser=, issueDate=1721036353617, maxDate=1721641153617, sequenceNumber=1635, masterKeyId=22)
24/07/15 11:39:13 INFO security.TokenCache: Got dt for hdfs://efrei; Kin
d: kms-dt, Service: kms://http@bigdata03.efrei.hadoop.clemlab.io:9292/km
s, Ident: (kms-dt owner=thomas.almeida, renewer=yarn, realUser=, issueDa
te=1721036353675, maxDate=1721641153675, sequenceNumber=1521, masterKeyId=8)
24/07/15 11:39:13 INFO mapreduce.JobResourceUploader: Disabling Erasure Coding for path: /user/thomas.almeida/.staging/job_1720701352744_0874   
24/07/15 11:39:14 INFO input.FileInputFormat: Total input files to process : 1
24/07/15 11:39:14 INFO mapreduce.JobSubmitter: number of splits:1
24/07/15 11:39:14 INFO mapreduce.JobSubmitter: Submitting tokens for job: job_1720701352744_0874
24/07/15 11:39:14 INFO mapreduce.JobSubmitter: Executing with tokens: [K
ind: kms-dt, Service: kms://http@bigdata03.efrei.hadoop.clemlab.io:9292/
kms, Ident: (kms-dt owner=thomas.almeida, renewer=yarn, realUser=, issue
Date=1721036353675, maxDate=1721641153675, sequenceNumber=1521, masterKe
yId=8), Kind: HDFS_DELEGATION_TOKEN, Service: ha-hdfs:efrei, Ident: (tok
en for thomas.almeida: HDFS_DELEGATION_TOKEN owner=thomas.almeida@EFREI.
HADOOP.CLEMLAB.IO, renewer=yarn, realUser=, issueDate=1721036353617, maxDate=1721641153617, sequenceNumber=1635, masterKeyId=22)]
24/07/15 11:39:14 INFO conf.Configuration: found resource resource-types.xml at file:/etc/hadoop/1.2.4.0-10/0/resource-types.xml
24/07/15 11:39:14 INFO impl.TimelineClientImpl: Timeline service address: bigdata02.efrei.hadoop.clemlab.io:8190
24/07/15 11:39:14 INFO impl.YarnClientImpl: Submitted application application_1720701352744_0874
24/07/15 11:39:14 INFO mapreduce.Job: The url to track the job: https://
bigdata01.efrei.hadoop.clemlab.io:8090/proxy/application_1720701352744_0874/
24/07/15 11:39:14 INFO mapreduce.Job: Running job: job_1720701352744_0874
24/07/15 11:39:21 INFO mapreduce.Job: Job job_1720701352744_0874 running in uber mode : false
24/07/15 11:39:21 INFO mapreduce.Job:  map 0% reduce 0%
24/07/15 11:39:27 INFO mapreduce.Job:  map 100% reduce 0%
24/07/15 11:39:31 INFO mapreduce.Job:  map 100% reduce 100%
24/07/15 11:39:31 INFO mapreduce.Job: Job job_1720701352744_0874 completed successfully
24/07/15 11:39:31 INFO mapreduce.Job: Counters: 54
        File System Counters
                FILE: Number of bytes read=176
                FILE: Number of bytes written=612797
                FILE: Number of read operations=0
                FILE: Number of large read operations=0
                FILE: Number of write operations=0
                HDFS: Number of bytes read=16787
                HDFS: Number of bytes written=80
                HDFS: Number of read operations=8
                HDFS: Number of large read operations=0
                HDFS: Number of write operations=2
                HDFS: Number of bytes read erasure-coded=0
        Job Counters
                Launched map tasks=1
                Launched reduce tasks=1
                Data-local map tasks=1
                Total time spent by all maps in occupied slots (ms)=11103
                Total time spent by all reduces in occupied slots (ms)=5392
                Total time spent by all map tasks (ms)=3701
                Total time spent by all reduce tasks (ms)=1348
                Total vcore-milliseconds taken by all map tasks=3701    
                Total vcore-milliseconds taken by all reduce tasks=1348 
                Total megabyte-milliseconds taken by all map tasks=5684736
                Total megabyte-milliseconds taken by all reduce tasks=2760704
        Map-Reduce Framework
                Map input records=98
                Map output records=97
                Map output bytes=776
                Map output materialized bytes=176
                Input split bytes=107
                Combine input records=97
                Combine output records=17
                Reduce input groups=17
                Reduce shuffle bytes=176
                Reduce input records=17
                Reduce output records=17
                Spilled Records=34
                Shuffled Maps =1
                Failed Shuffles=0
                Merged Map outputs=1
                GC time elapsed (ms)=68
                CPU time spent (ms)=1050
                Physical memory (bytes) snapshot=1551527936
                Virtual memory (bytes) snapshot=6700388352
                Total committed heap usage (bytes)=1608515584
                Peak Map Physical memory (bytes)=1202548736
                Peak Map Virtual memory (bytes)=3111260160
                Peak Reduce Physical memory (bytes)=348979200
                Peak Reduce Virtual memory (bytes)=3589128192
        Shuffle Errors
                BAD_ID=0
                CONNECTION=0
                IO_ERROR=0
                WRONG_LENGTH=0
                WRONG_MAP=0
                WRONG_REDUCE=0
        File Input Format Counters
                Bytes Read=16680
        File Output Format Counters
                Bytes Written=80
cat: `/user/thomas.almeida/output_districts/part-00000': No such file or directory
[thomas.almeida@bigdata01 ~]$ hdfs dfs -cat /user/thomas.almeida/output_districts/part-r-00000
3       1
4       1
5       2
6       1
7       3
8       5
9       1
11      1
12      29
13      2
14      3
15      1
16      36
17      1
18      1
19      6
20      3
`


### 1.8.2 Show all existing species (very easy)
Write a MapReduce job that displays the list of different species trees in this file.
`[thomas.almeida@bigdata01 ~]$ hdfs dfs -rm -r /user/thomas.almeida/output_species
yarn jar /home/thomas.almeida/hadoop-examples-mapreduce-1.0-SNAPSHOT-jar-with-dependencies.jar species /user/thomas.almeida/trees.csv /user/thomas.almeida/output_species
hdfs dfs -cat /user/thomas.almeida/output_species/part-r-00000
rm: `/user/thomas.almeida/output_species': No such file or directory
24/07/15 11:43:24 INFO client.AHSProxy: Connecting to Application History server at bigdata02.efrei.hadoop.clemlab.io/62.210.145.80:10200       
24/07/15 11:43:24 INFO hdfs.DFSClient: Created token for thomas.almeida:
 HDFS_DELEGATION_TOKEN owner=thomas.almeida@EFREI.HADOOP.CLEMLAB.IO, ren
ewer=yarn, realUser=, issueDate=1721036604153, maxDate=1721641404153, sequenceNumber=1646, masterKeyId=22 on ha-hdfs:efrei
24/07/15 11:43:24 INFO kms.KMSClientProvider: New token created: (Kind: 
kms-dt, Service: kms://http@bigdata03.efrei.hadoop.clemlab.io:9292/kms, 
Ident: (kms-dt owner=thomas.almeida, renewer=yarn, realUser=, issueDate=
1721036604212, maxDate=1721641404212, sequenceNumber=1532, masterKeyId=8))
24/07/15 11:43:24 INFO security.TokenCache: Got dt for hdfs://efrei; Kin
d: HDFS_DELEGATION_TOKEN, Service: ha-hdfs:efrei, Ident: (token for thom
as.almeida: HDFS_DELEGATION_TOKEN owner=thomas.almeida@EFREI.HADOOP.CLEM
LAB.IO, renewer=yarn, realUser=, issueDate=1721036604153, maxDate=1721641404153, sequenceNumber=1646, masterKeyId=22)
24/07/15 11:43:24 INFO security.TokenCache: Got dt for hdfs://efrei; Kin
d: kms-dt, Service: kms://http@bigdata03.efrei.hadoop.clemlab.io:9292/km
s, Ident: (kms-dt owner=thomas.almeida, renewer=yarn, realUser=, issueDa
te=1721036604212, maxDate=1721641404212, sequenceNumber=1532, masterKeyId=8)
^[[A24/07/15 11:43:24 INFO mapreduce.JobResourceUploader: Disabling Eras
ure Coding for path: /user/thomas.almeida/.staging/job_1720701352744_0885
24/07/15 11:43:24 INFO input.FileInputFormat: Total input files to process : 1
24/07/15 11:43:24 INFO mapreduce.JobSubmitter: number of splits:1       
24/07/15 11:43:24 INFO mapreduce.JobSubmitter: Submitting tokens for job: job_1720701352744_0885
24/07/15 11:43:24 INFO mapreduce.JobSubmitter: Executing with tokens: [K
ind: kms-dt, Service: kms://http@bigdata03.efrei.hadoop.clemlab.io:9292/
kms, Ident: (kms-dt owner=thomas.almeida, renewer=yarn, realUser=, issue
Date=1721036604212, maxDate=1721641404212, sequenceNumber=1532, masterKe
yId=8), Kind: HDFS_DELEGATION_TOKEN, Service: ha-hdfs:efrei, Ident: (tok
en for thomas.almeida: HDFS_DELEGATION_TOKEN owner=thomas.almeida@EFREI.
HADOOP.CLEMLAB.IO, renewer=yarn, realUser=, issueDate=1721036604153, maxDate=1721641404153, sequenceNumber=1646, masterKeyId=22)]
24/07/15 11:43:24 INFO conf.Configuration: found resource resource-types.xml at file:/etc/hadoop/1.2.4.0-10/0/resource-types.xml
24/07/15 11:43:24 INFO impl.TimelineClientImpl: Timeline service address: bigdata02.efrei.hadoop.clemlab.io:8190
24/07/15 11:43:25 INFO impl.YarnClientImpl: Submitted application application_1720701352744_0885
24/07/15 11:43:25 INFO mapreduce.Job: The url to track the job: https://
bigdata01.efrei.hadoop.clemlab.io:8090/proxy/application_1720701352744_0885/
24/07/15 11:43:25 INFO mapreduce.Job: Running job: job_1720701352744_0885
24/07/15 11:43:31 INFO mapreduce.Job: Job job_1720701352744_0885 running in uber mode : false
24/07/15 11:43:31 INFO mapreduce.Job:  map 0% reduce 0%
24/07/15 11:43:37 INFO mapreduce.Job:  map 100% reduce 0%
24/07/15 11:43:41 INFO mapreduce.Job:  map 100% reduce 100%
24/07/15 11:43:41 INFO mapreduce.Job: Job job_1720701352744_0885 completed successfully
24/07/15 11:43:41 INFO mapreduce.Job: Counters: 54
        File System Counters
                FILE: Number of bytes read=547
                FILE: Number of bytes written=613515
                FILE: Number of read operations=0
                FILE: Number of large read operations=0
                FILE: Number of write operations=0
                HDFS: Number of bytes read=16787
                HDFS: Number of bytes written=451
                HDFS: Number of read operations=8
                HDFS: Number of large read operations=0
                HDFS: Number of write operations=2
                HDFS: Number of bytes read erasure-coded=0
        Job Counters
                Launched map tasks=1
                Launched reduce tasks=1
                Data-local map tasks=1
                Total time spent by all maps in occupied slots (ms)=11277
                Total time spent by all reduces in occupied slots (ms)=5540
                Total time spent by all map tasks (ms)=3759
                Total time spent by all reduce tasks (ms)=1385
                Total vcore-milliseconds taken by all map tasks=3759    
                Total vcore-milliseconds taken by all reduce tasks=1385 
                Total megabyte-milliseconds taken by all map tasks=5773824
                Total megabyte-milliseconds taken by all reduce tasks=2836480
        Map-Reduce Framework
                Map input records=98
                Map output records=97
                Map output bytes=995
                Map output materialized bytes=547
                Input split bytes=107
                Combine input records=97
                Combine output records=45
                Reduce input groups=45
                Reduce shuffle bytes=547
                Reduce input records=45
                Reduce output records=45
                Spilled Records=90
                Shuffled Maps =1
                Failed Shuffles=0
                Merged Map outputs=1
                GC time elapsed (ms)=74
                CPU time spent (ms)=1060
                Physical memory (bytes) snapshot=1529217024
                Virtual memory (bytes) snapshot=6701441024
                Total committed heap usage (bytes)=1515716608
                Peak Map Physical memory (bytes)=1197277184
                Peak Map Virtual memory (bytes)=3114340352
                Peak Reduce Physical memory (bytes)=331939840
                Peak Reduce Virtual memory (bytes)=3587100672
        Shuffle Errors
                BAD_ID=0
                CONNECTION=0
                IO_ERROR=0
                WRONG_LENGTH=0
                WRONG_MAP=0
                WRONG_REDUCE=0
        File Input Format Counters
                Bytes Read=16680
        File Output Format Counters
                Bytes Written=451
araucana
atlantica
australis
baccata
bignonioides
biloba
bungeana
cappadocicum
carpinifolia
colurna
coulteri
decurrens
dioicus
distichum
excelsior
fraxinifolia
giganteum
giraldii
glutinosa
grandiflora
hippocastanum
ilex
involucrata
japonicum
kaki
libanii
monspessulanum
nigra
nigra laricio
opalus
orientalis
papyrifera
petraea
pomifera
pseudoacacia
sempervirens
serrata
stenoptera
suber
sylvatica
tomentosa
tulipifera
ulmoides
virginiana
x acerifolia
`



### 1.8.3 Number of trees by kinds (easy)
Write a MapReduce job that calculates the number of trees of each kind. For example, there are 3 Acer, 19 Platanus, etc. How will you define the keys and values passed between the mapper and the reducer? The mapper must extract the kind of tree. The reducer gets the pairs (keyI, valueI) with the same key, so this key must be the kind of tree; the value being the number of such trees.

`[thomas.almeida@bigdata01 ~]$ hdfs dfs -rm -r /user/thomas.almeida/output_treeskind
yarn jar /home/thomas.almeida/hadoop-examples-mapreduce-1.0-SNAPSHOT-jar-with-dependencies.jar treeskind /user/thomas.almeida/trees.csv /user/thomas.almeida/output_treeskind
hdfs dfs -cat /user/thomas.almeida/output_treeskind/part-r-00000        
rm: `/user/thomas.almeida/output_treeskind': No such file or directory
24/07/15 11:46:16 INFO client.AHSProxy: Connecting to Application History server at bigdata02.efrei.hadoop.clemlab.io/62.210.145.80:10200       
24/07/15 11:46:16 INFO hdfs.DFSClient: Created token for thomas.almeida:
 HDFS_DELEGATION_TOKEN owner=thomas.almeida@EFREI.HADOOP.CLEMLAB.IO, ren
ewer=yarn, realUser=, issueDate=1721036776693, maxDate=1721641576693, sequenceNumber=1657, masterKeyId=22 on ha-hdfs:efrei
24/07/15 11:46:16 INFO kms.KMSClientProvider: New token created: (Kind: 
kms-dt, Service: kms://http@bigdata03.efrei.hadoop.clemlab.io:9292/kms, 
Ident: (kms-dt owner=thomas.almeida, renewer=yarn, realUser=, issueDate=
1721036776750, maxDate=1721641576750, sequenceNumber=1543, masterKeyId=8))
24/07/15 11:46:16 INFO security.TokenCache: Got dt for hdfs://efrei; Kin
d: HDFS_DELEGATION_TOKEN, Service: ha-hdfs:efrei, Ident: (token for thom
as.almeida: HDFS_DELEGATION_TOKEN owner=thomas.almeida@EFREI.HADOOP.CLEM
LAB.IO, renewer=yarn, realUser=, issueDate=1721036776693, maxDate=1721641576693, sequenceNumber=1657, masterKeyId=22)
24/07/15 11:46:16 INFO security.TokenCache: Got dt for hdfs://efrei; Kin
d: kms-dt, Service: kms://http@bigdata03.efrei.hadoop.clemlab.io:9292/km
s, Ident: (kms-dt owner=thomas.almeida, renewer=yarn, realUser=, issueDa
te=1721036776750, maxDate=1721641576750, sequenceNumber=1543, masterKeyId=8)
24/07/15 11:46:16 INFO mapreduce.JobResourceUploader: Disabling Erasure Coding for path: /user/thomas.almeida/.staging/job_1720701352744_0896   
24/07/15 11:46:17 INFO input.FileInputFormat: Total input files to process : 1
24/07/15 11:46:17 INFO mapreduce.JobSubmitter: number of splits:1
24/07/15 11:46:17 INFO mapreduce.JobSubmitter: Submitting tokens for job: job_1720701352744_0896
24/07/15 11:46:17 INFO mapreduce.JobSubmitter: Executing with tokens: [K
ind: kms-dt, Service: kms://http@bigdata03.efrei.hadoop.clemlab.io:9292/
kms, Ident: (kms-dt owner=thomas.almeida, renewer=yarn, realUser=, issue
Date=1721036776750, maxDate=1721641576750, sequenceNumber=1543, masterKe
yId=8), Kind: HDFS_DELEGATION_TOKEN, Service: ha-hdfs:efrei, Ident: (tok
en for thomas.almeida: HDFS_DELEGATION_TOKEN owner=thomas.almeida@EFREI.
HADOOP.CLEMLAB.IO, renewer=yarn, realUser=, issueDate=1721036776693, maxDate=1721641576693, sequenceNumber=1657, masterKeyId=22)]
24/07/15 11:46:17 INFO conf.Configuration: found resource resource-types.xml at file:/etc/hadoop/1.2.4.0-10/0/resource-types.xml
24/07/15 11:46:17 INFO impl.TimelineClientImpl: Timeline service address: bigdata02.efrei.hadoop.clemlab.io:8190
24/07/15 11:46:18 INFO impl.YarnClientImpl: Submitted application application_1720701352744_0896
24/07/15 11:46:18 INFO mapreduce.Job: The url to track the job: https://
bigdata01.efrei.hadoop.clemlab.io:8090/proxy/application_1720701352744_0896/
24/07/15 11:46:18 INFO mapreduce.Job: Running job: job_1720701352744_0896
24/07/15 11:46:25 INFO mapreduce.Job: Job job_1720701352744_0896 running in uber mode : false
24/07/15 11:46:25 INFO mapreduce.Job:  map 0% reduce 0%
24/07/15 11:46:31 INFO mapreduce.Job:  map 100% reduce 0%
24/07/15 11:46:37 INFO mapreduce.Job:  map 100% reduce 100%
24/07/15 11:46:37 INFO mapreduce.Job: Job job_1720701352744_0896 completed successfully
24/07/15 11:46:37 INFO mapreduce.Job: Counters: 54
        File System Counters
                FILE: Number of bytes read=727
                FILE: Number of bytes written=613893
                FILE: Number of read operations=0
                FILE: Number of large read operations=0
                FILE: Number of write operations=0
                HDFS: Number of bytes read=16787
                HDFS: Number of bytes written=631
                HDFS: Number of read operations=8
                HDFS: Number of large read operations=0
                HDFS: Number of write operations=2
                HDFS: Number of bytes read erasure-coded=0
        Job Counters
                Launched map tasks=1
                Launched reduce tasks=1
                Data-local map tasks=1
                Total time spent by all maps in occupied slots (ms)=11412
                Total time spent by all reduces in occupied slots (ms)=15136
                Total time spent by all map tasks (ms)=3804
                Total time spent by all reduce tasks (ms)=3784
                Total vcore-milliseconds taken by all map tasks=3804    
                Total vcore-milliseconds taken by all reduce tasks=3784 
                Total megabyte-milliseconds taken by all map tasks=5842944
                Total megabyte-milliseconds taken by all reduce tasks=7749632
        Map-Reduce Framework
                Map input records=98
                Map output records=97
                Map output bytes=1383
                Map output materialized bytes=727
                Input split bytes=107
                Combine input records=97
                Combine output records=45
                Reduce input groups=45
                Reduce shuffle bytes=727
                Reduce input records=45
                Reduce output records=45
                Spilled Records=90
                Shuffled Maps =1
                Failed Shuffles=0
                Merged Map outputs=1
                GC time elapsed (ms)=67
                CPU time spent (ms)=1060
                Physical memory (bytes) snapshot=1529126912
                Virtual memory (bytes) snapshot=6702247936
                Total committed heap usage (bytes)=1527250944
                Peak Map Physical memory (bytes)=1193807872
                Peak Map Virtual memory (bytes)=3111215104
                Peak Reduce Physical memory (bytes)=335319040
                Peak Reduce Virtual memory (bytes)=3591032832
        Shuffle Errors
                BAD_ID=0
                CONNECTION=0
                IO_ERROR=0
                WRONG_LENGTH=0
                WRONG_MAP=0
                WRONG_REDUCE=0
        File Input Format Counters
                Bytes Read=16680
        File Output Format Counters
                Bytes Written=631
araucana        1
atlantica       4
australis       8
baccata 14
bignonioides    21
biloba  33
bungeana        46
cappadocicum    60
carpinifolia    78
colurna 99
coulteri        121
decurrens       144
dioicus 168
distichum       195
excelsior       223
fraxinifolia    253
giganteum       288
giraldii        324
glutinosa       361
grandiflora     399
hippocastanum   440
ilex    482
involucrata     525
japonicum       569
kaki    615
libanii 663
monspessulanum  712
nigra   764
nigra laricio   817
opalus  871
orientalis      933
papyrifera      996
petraea 1061
pomifera        1127
pseudoacacia    1194
sempervirens    1262
serrata 1331
stenoptera      1401
suber   1472
sylvatica       1551
tomentosa       1632
tulipifera      1715
ulmoides        1799
virginiana      1885
x acerifolia    1982
`



### 1.8.4 Maximum height per kind of tree (average)
Write a MapReduce job that calculates the height of the tallest tree of each kind. For example, the tallest Acer is 16m, the tallest Platanus is 45m, etc.

`[thomas.almeida@bigdata01 ~]$ hdfs dfs -rm -r /user/thomas.almeida/output_maxheightkind
yarn jar /home/thomas.almeida/hadoop-examples-mapreduce-1.0-SNAPSHOT-jar-with-dependencies.jar maxheightkind /user/thomas.almeida/trees.csv /user/thomas.almeida/output_maxheightkind
hdfs dfs -cat /user/thomas.almeida/output_maxheightkind/part-r-00000    
rm: `/user/thomas.almeida/output_maxheightkind': No such file or directory
24/07/15 11:47:08 INFO client.AHSProxy: Connecting to Application History server at bigdata02.efrei.hadoop.clemlab.io/62.210.145.80:10200       
24/07/15 11:47:09 INFO hdfs.DFSClient: Created token for thomas.almeida:
 HDFS_DELEGATION_TOKEN owner=thomas.almeida@EFREI.HADOOP.CLEMLAB.IO, ren
ewer=yarn, realUser=, issueDate=1721036829103, maxDate=1721641629103, sequenceNumber=1659, masterKeyId=22 on ha-hdfs:efrei
24/07/15 11:47:09 INFO kms.KMSClientProvider: New token created: (Kind: 
kms-dt, Service: kms://http@bigdata03.efrei.hadoop.clemlab.io:9292/kms, 
Ident: (kms-dt owner=thomas.almeida, renewer=yarn, realUser=, issueDate=
1721036829159, maxDate=1721641629159, sequenceNumber=1545, masterKeyId=8))
24/07/15 11:47:09 INFO security.TokenCache: Got dt for hdfs://efrei; Kin
d: HDFS_DELEGATION_TOKEN, Service: ha-hdfs:efrei, Ident: (token for thom
as.almeida: HDFS_DELEGATION_TOKEN owner=thomas.almeida@EFREI.HADOOP.CLEM
LAB.IO, renewer=yarn, realUser=, issueDate=1721036829103, maxDate=1721641629103, sequenceNumber=1659, masterKeyId=22)
24/07/15 11:47:09 INFO security.TokenCache: Got dt for hdfs://efrei; Kin
d: kms-dt, Service: kms://http@bigdata03.efrei.hadoop.clemlab.io:9292/km
s, Ident: (kms-dt owner=thomas.almeida, renewer=yarn, realUser=, issueDa
te=1721036829159, maxDate=1721641629159, sequenceNumber=1545, masterKeyId=8)
24/07/15 11:47:09 INFO mapreduce.JobResourceUploader: Disabling Erasure Coding for path: /user/thomas.almeida/.staging/job_1720701352744_0898   
24/07/15 11:47:09 INFO input.FileInputFormat: Total input files to process : 1
24/07/15 11:47:09 INFO mapreduce.JobSubmitter: number of splits:1
24/07/15 11:47:09 INFO mapreduce.JobSubmitter: Submitting tokens for job: job_1720701352744_0898
24/07/15 11:47:09 INFO mapreduce.JobSubmitter: Executing with tokens: [K
ind: kms-dt, Service: kms://http@bigdata03.efrei.hadoop.clemlab.io:9292/
kms, Ident: (kms-dt owner=thomas.almeida, renewer=yarn, realUser=, issue
Date=1721036829159, maxDate=1721641629159, sequenceNumber=1545, masterKe
yId=8), Kind: HDFS_DELEGATION_TOKEN, Service: ha-hdfs:efrei, Ident: (tok
en for thomas.almeida: HDFS_DELEGATION_TOKEN owner=thomas.almeida@EFREI.
HADOOP.CLEMLAB.IO, renewer=yarn, realUser=, issueDate=1721036829103, maxDate=1721641629103, sequenceNumber=1659, masterKeyId=22)]
24/07/15 11:47:09 INFO conf.Configuration: found resource resource-types.xml at file:/etc/hadoop/1.2.4.0-10/0/resource-types.xml
24/07/15 11:47:09 INFO impl.TimelineClientImpl: Timeline service address: bigdata02.efrei.hadoop.clemlab.io:8190
24/07/15 11:47:10 INFO impl.YarnClientImpl: Submitted application application_1720701352744_0898
24/07/15 11:47:10 INFO mapreduce.Job: The url to track the job: https://
bigdata01.efrei.hadoop.clemlab.io:8090/proxy/application_1720701352744_0898/
24/07/15 11:47:10 INFO mapreduce.Job: Running job: job_1720701352744_0898
24/07/15 11:47:16 INFO mapreduce.Job: Job job_1720701352744_0898 running in uber mode : false
24/07/15 11:47:16 INFO mapreduce.Job:  map 0% reduce 0%
24/07/15 11:47:22 INFO mapreduce.Job:  map 100% reduce 0%
24/07/15 11:47:25 INFO mapreduce.Job:  map 100% reduce 100%
24/07/15 11:47:26 INFO mapreduce.Job: Job job_1720701352744_0898 completed successfully
24/07/15 11:47:26 INFO mapreduce.Job: Counters: 54
        File System Counters
                FILE: Number of bytes read=727
                FILE: Number of bytes written=613937
                FILE: Number of read operations=0
                FILE: Number of large read operations=0
                FILE: Number of write operations=0
                HDFS: Number of bytes read=16787
                HDFS: Number of bytes written=675
                HDFS: Number of read operations=8
                HDFS: Number of large read operations=0
                HDFS: Number of write operations=2
                HDFS: Number of bytes read erasure-coded=0
        Job Counters
                Launched map tasks=1
                Launched reduce tasks=1
                Data-local map tasks=1
                Total time spent by all maps in occupied slots (ms)=11253
                Total time spent by all reduces in occupied slots (ms)=5560
                Total time spent by all map tasks (ms)=3751
                Total time spent by all reduce tasks (ms)=1390
                Total vcore-milliseconds taken by all map tasks=3751    
                Total vcore-milliseconds taken by all reduce tasks=1390 
                Total megabyte-milliseconds taken by all map tasks=5761536
                Total megabyte-milliseconds taken by all reduce tasks=2846720
        Map-Reduce Framework
                Map input records=98
                Map output records=96
                Map output bytes=1369
                Map output materialized bytes=727
                Input split bytes=107
                Combine input records=96
                Combine output records=45
                Reduce input groups=45
                Reduce shuffle bytes=727
                Reduce input records=45
                Reduce output records=45
                Spilled Records=90
                Shuffled Maps =1
                Failed Shuffles=0
                Merged Map outputs=1
                GC time elapsed (ms)=73
                CPU time spent (ms)=1070
                Physical memory (bytes) snapshot=1536516096
                Virtual memory (bytes) snapshot=6702567424
                Total committed heap usage (bytes)=1520435200
                Peak Map Physical memory (bytes)=1199161344
                Peak Map Virtual memory (bytes)=3111616512
                Peak Reduce Physical memory (bytes)=337354752
                Peak Reduce Virtual memory (bytes)=3590950912
        Shuffle Errors
                BAD_ID=0
                CONNECTION=0
                IO_ERROR=0
                WRONG_LENGTH=0
                WRONG_MAP=0
                WRONG_REDUCE=0
        File Input Format Counters
                Bytes Read=16680
        File Output Format Counters
                Bytes Written=675
araucana        9.0
atlantica       25.0
australis       16.0
baccata 13.0
bignonioides    15.0
biloba  33.0
bungeana        10.0
cappadocicum    16.0
carpinifolia    30.0
colurna 20.0
coulteri        14.0
decurrens       20.0
dioicus 10.0
distichum       35.0
excelsior       30.0
fraxinifolia    27.0
giganteum       35.0
giraldii        35.0
glutinosa       16.0
grandiflora     12.0
hippocastanum   30.0
ilex    15.0
involucrata     12.0
japonicum       10.0
kaki    14.0
libanii 30.0
monspessulanum  12.0
nigra   30.0
nigra laricio   30.0
opalus  15.0
orientalis      34.0
papyrifera      12.0
petraea 31.0
pomifera        13.0
pseudoacacia    11.0
sempervirens    30.0
serrata 18.0
stenoptera      30.0
suber   10.0
sylvatica       30.0
tomentosa       20.0
tulipifera      35.0
ulmoides        12.0
virginiana      14.0
x acerifolia    45.0
`

### 1.8.5 Sort the trees height from smallest to largest (average)
Write a MapReduce job that sorts the trees' height from smallest to largest.

`[thomas.almeida@bigdata01 ~]$ hdfs dfs -rm -r /user/thomas.almeida/output_sortTrees
yarn jar /home/thomas.almeida/hadoop-examples-mapreduce-1.0-SNAPSHOT-jar-with-dependencies.jar sortTrees /user/thomas.almeida/trees.csv /user/thomas.almeida/output_sortTrees
hdfs dfs -cat /user/thomas.almeida/output_sortTrees/part-r-00000        
rm: `/user/thomas.almeida/output_sortTrees': No such file or directory
24/07/15 11:47:47 INFO client.AHSProxy: Connecting to Application History server at bigdata02.efrei.hadoop.clemlab.io/62.210.145.80:10200       
24/07/15 11:47:47 INFO hdfs.DFSClient: Created token for thomas.almeida:
 HDFS_DELEGATION_TOKEN owner=thomas.almeida@EFREI.HADOOP.CLEMLAB.IO, ren
ewer=yarn, realUser=, issueDate=1721036867304, maxDate=1721641667304, sequenceNumber=1660, masterKeyId=22 on ha-hdfs:efrei
24/07/15 11:47:47 INFO kms.KMSClientProvider: New token created: (Kind: 
kms-dt, Service: kms://http@bigdata03.efrei.hadoop.clemlab.io:9292/kms, 
Ident: (kms-dt owner=thomas.almeida, renewer=yarn, realUser=, issueDate=
1721036867363, maxDate=1721641667363, sequenceNumber=1546, masterKeyId=8))
24/07/15 11:47:47 INFO security.TokenCache: Got dt for hdfs://efrei; Kin
d: HDFS_DELEGATION_TOKEN, Service: ha-hdfs:efrei, Ident: (token for thom
as.almeida: HDFS_DELEGATION_TOKEN owner=thomas.almeida@EFREI.HADOOP.CLEM
LAB.IO, renewer=yarn, realUser=, issueDate=1721036867304, maxDate=1721641667304, sequenceNumber=1660, masterKeyId=22)
24/07/15 11:47:47 INFO security.TokenCache: Got dt for hdfs://efrei; Kin
d: kms-dt, Service: kms://http@bigdata03.efrei.hadoop.clemlab.io:9292/km
s, Ident: (kms-dt owner=thomas.almeida, renewer=yarn, realUser=, issueDa
te=1721036867363, maxDate=1721641667363, sequenceNumber=1546, masterKeyId=8)
24/07/15 11:47:47 INFO mapreduce.JobResourceUploader: Disabling Erasure Coding for path: /user/thomas.almeida/.staging/job_1720701352744_0899   
24/07/15 11:47:47 INFO input.FileInputFormat: Total input files to process : 1
24/07/15 11:47:47 INFO mapreduce.JobSubmitter: number of splits:1
24/07/15 11:47:47 INFO mapreduce.JobSubmitter: Submitting tokens for job: job_1720701352744_0899
24/07/15 11:47:47 INFO mapreduce.JobSubmitter: Executing with tokens: [K
ind: kms-dt, Service: kms://http@bigdata03.efrei.hadoop.clemlab.io:9292/
kms, Ident: (kms-dt owner=thomas.almeida, renewer=yarn, realUser=, issue
Date=1721036867363, maxDate=1721641667363, sequenceNumber=1546, masterKe
yId=8), Kind: HDFS_DELEGATION_TOKEN, Service: ha-hdfs:efrei, Ident: (tok
en for thomas.almeida: HDFS_DELEGATION_TOKEN owner=thomas.almeida@EFREI.
HADOOP.CLEMLAB.IO, renewer=yarn, realUser=, issueDate=1721036867304, maxDate=1721641667304, sequenceNumber=1660, masterKeyId=22)]
24/07/15 11:47:48 INFO conf.Configuration: found resource resource-types.xml at file:/etc/hadoop/1.2.4.0-10/0/resource-types.xml
24/07/15 11:47:48 INFO impl.TimelineClientImpl: Timeline service address: bigdata02.efrei.hadoop.clemlab.io:8190
24/07/15 11:47:48 INFO impl.YarnClientImpl: Submitted application application_1720701352744_0899
24/07/15 11:47:48 INFO mapreduce.Job: The url to track the job: https://
bigdata01.efrei.hadoop.clemlab.io:8090/proxy/application_1720701352744_0899/
24/07/15 11:47:48 INFO mapreduce.Job: Running job: job_1720701352744_0899
24/07/15 11:47:54 INFO mapreduce.Job: Job job_1720701352744_0899 running in uber mode : false
24/07/15 11:47:54 INFO mapreduce.Job:  map 0% reduce 0%
24/07/15 11:48:00 INFO mapreduce.Job:  map 100% reduce 0%
24/07/15 11:48:03 INFO mapreduce.Job:  map 100% reduce 100%
24/07/15 11:48:04 INFO mapreduce.Job: Job job_1720701352744_0899 completed successfully
24/07/15 11:48:04 INFO mapreduce.Job: Counters: 54
        File System Counters
                FILE: Number of bytes read=4100
                FILE: Number of bytes written=621015
                FILE: Number of read operations=0
                FILE: Number of large read operations=0
                FILE: Number of write operations=0
                HDFS: Number of bytes read=16787
                HDFS: Number of bytes written=3994
                HDFS: Number of read operations=8
                HDFS: Number of large read operations=0
                HDFS: Number of write operations=2
                HDFS: Number of bytes read erasure-coded=0
        Job Counters
                Launched map tasks=1
                Launched reduce tasks=1
                Data-local map tasks=1
                Total time spent by all maps in occupied slots (ms)=11394
                Total time spent by all reduces in occupied slots (ms)=5568
                Total time spent by all map tasks (ms)=3798
                Total time spent by all reduce tasks (ms)=1392
                Total vcore-milliseconds taken by all map tasks=3798    
                Total vcore-milliseconds taken by all reduce tasks=1392 
                Total megabyte-milliseconds taken by all map tasks=5833728
                Total megabyte-milliseconds taken by all reduce tasks=2850816
        Map-Reduce Framework
                Map input records=98
                Map output records=96
                Map output bytes=3902
                Map output materialized bytes=4100
                Input split bytes=107
                Combine input records=0
                Combine output records=0
                Reduce input groups=28
                Reduce shuffle bytes=4100
                Reduce input records=96
                Reduce output records=96
                Spilled Records=192
                Shuffled Maps =1
                Failed Shuffles=0
                Merged Map outputs=1
                GC time elapsed (ms)=66
                CPU time spent (ms)=1040
                Physical memory (bytes) snapshot=1538007040
                Virtual memory (bytes) snapshot=6705635328
                Total committed heap usage (bytes)=1520959488
                Peak Map Physical memory (bytes)=1199677440
                Peak Map Virtual memory (bytes)=3114446848
                Peak Reduce Physical memory (bytes)=338329600
                Peak Reduce Virtual memory (bytes)=3591188480
        Shuffle Errors
                BAD_ID=0
                CONNECTION=0
                IO_ERROR=0
                WRONG_LENGTH=0
                WRONG_MAP=0
                WRONG_REDUCE=0
        File Input Format Counters
                Bytes Read=16680
        File Output Format Counters
                Bytes Written=3994
3 - Fagus sylvatica (Fagaceae)  2.0
89 - Taxus baccata (Taxaceae)   5.0
62 - Cedrus atlantica (Pinaceae)        6.0
39 - Araucaria araucana (Araucariaceae) 9.0
44 - Styphnolobium japonicum (Fabaceae) 10.0
32 - Quercus suber (Fagaceae)   10.0
95 - Pinus bungeana (Pinaceae)  10.0
61 - Gymnocladus dioicus (Fabaceae)     10.0
63 - Fagus sylvatica (Fagaceae) 10.0
4 - Robinia pseudoacacia (Fabaceae)     11.0
93 - Diospyros virginiana (Ebenaceae)   12.0
66 - Magnolia grandiflora (Magnoliaceae)        12.0
50 - Zelkova carpinifolia (Ulmaceae)    12.0
7 - Eucommia ulmoides (Eucomiaceae)     12.0
48 - Acer monspessulanum (Sapindacaees) 12.0
58 - Diospyros kaki (Ebenaceae) 12.0
33 - Broussonetia papyrifera (Moraceae) 12.0
71 - Davidia involucrata (Cornaceae)    12.0
36 - Taxus baccata (Taxaceae)   13.0
6 - Maclura pomifera (Moraceae) 13.0
68 - Diospyros kaki (Ebenaceae) 14.0
96 - Pinus coulteri (Pinaceae)  14.0
94 - Diospyros virginiana (Ebenaceae)   14.0
91 - Acer opalus (Sapindaceae)  15.0
5 - Catalpa bignonioides (Bignoniaceae) 15.0
70 - Fagus sylvatica (Fagaceae) 15.0
2 - Ulmus carpinifolia (Ulmaceae)       15.0
98 - Quercus ilex (Fagaceae)    15.0
28 - Alnus glutinosa (Betulaceae)       16.0
78 - Acer cappadocicum (Sapindaceae)    16.0
75 - Zelkova carpinifolia (Ulmaceae)    16.0
16 - Celtis australis (Cannabaceae)     16.0
64 - Ginkgo biloba (Ginkgoaceae)        18.0
83 - Zelkova serrata (Ulmaceae) 18.0
23 - Aesculus hippocastanum (Sapindaceae)       18.0
60 - Fagus sylvatica (Fagaceae) 18.0
34 - Corylus colurna (Betulaceae)       20.0
51 - Platanus x acerifolia (Platanaceae)        20.0
43 - Tilia tomentosa (Malvaceae)        20.0
15 - Corylus colurna (Betulaceae)       20.0
11 - Calocedrus decurrens (Cupressaceae)        20.0
1 - Corylus colurna (Betulaceae)        20.0
8 - Platanus orientalis (Platanaceae)   20.0
20 - Fagus sylvatica (Fagaceae) 20.0
35 - Paulownia tomentosa (Paulowniaceae)        20.0
12 - Sequoiadendron giganteum (Taxodiaceae)     20.0
87 - Taxodium distichum (Taxodiaceae)   20.0
13 - Platanus orientalis (Platanaceae)  20.0
10 - Ginkgo biloba (Ginkgoaceae)        22.0
47 - Aesculus hippocastanum (Sapindaceae)       22.0
86 - Platanus orientalis (Platanaceae)  22.0
14 - Pterocarya fraxinifolia (Juglandaceae)     22.0
88 - Liriodendron tulipifera (Magnoliaceae)     22.0
18 - Fagus sylvatica (Fagaceae) 23.0
24 - Cedrus atlantica (Pinaceae)        25.0
31 - Ginkgo biloba (Ginkgoaceae)        25.0
92 - Platanus x acerifolia (Platanaceae)        25.0
49 - Platanus orientalis (Platanaceae)  25.0
97 - Pinus nigra (Pinaceae)     25.0
84 - Ginkgo biloba (Ginkgoaceae)        25.0
73 - Platanus orientalis (Platanaceae)  26.0
65 - Pterocarya fraxinifolia (Juglandaceae)     27.0
42 - Platanus orientalis (Platanaceae)  27.0
85 - Juglans nigra (Juglandaceae)       28.0
76 - Pinus nigra laricio (Pinaceae)     30.0
19 - Quercus petraea (Fagaceae) 30.0
72 - Sequoiadendron giganteum (Taxodiaceae)     30.0
54 - Pterocarya stenoptera (Juglandaceae)       30.0
29 - Zelkova carpinifolia (Ulmaceae)    30.0
27 - Sequoia sempervirens (Taxodiaceae) 30.0
25 - Fagus sylvatica (Fagaceae) 30.0
41 - Platanus x acerifolia (Platanaceae)        30.0
77 - Taxodium distichum (Taxodiaceae)   30.0
55 - Platanus x acerifolia (Platanaceae)        30.0
69 - Pinus nigra (Pinaceae)     30.0
38 - Fagus sylvatica (Fagaceae) 30.0
59 - Sequoiadendron giganteum (Taxodiaceae)     30.0
52 - Fraxinus excelsior (Oleaceae)      30.0
37 - Cedrus libanii (Pinaceae)  30.0
22 - Cedrus libanii (Pinaceae)  30.0
30 - Aesculus hippocastanum (Sapindaceae)       30.0
80 - Quercus petraea (Fagaceae) 31.0
9 - Platanus orientalis (Platanaceae)   31.0
82 - Platanus x acerifolia (Platanaceae)        32.0
46 - Ginkgo biloba (Ginkgoaceae)        33.0
45 - Platanus orientalis (Platanaceae)  34.0
56 - Taxodium distichum (Taxodiaceae)   35.0
81 - Liriodendron tulipifera (Magnoliaceae)     35.0
17 - Platanus x acerifolia (Platanaceae)        35.0
53 - Ailanthus giraldii (Simaroubaceae) 35.0
57 - Sequoiadendron giganteum (Taxodiaceae)     35.0
26 - Platanus x acerifolia (Platanaceae)        40.0
74 - Platanus x acerifolia (Platanaceae)        40.0
40 - Platanus x acerifolia (Platanaceae)        40.0
90 - Platanus x acerifolia (Platanaceae)        42.0
21 - Platanus x acerifolia (Platanaceae)        45.0
`

### 1.8.6 District containing the oldest tree (difficult)
Write a MapReduce job that displays the district where the oldest tree is. The mapper must extract the age and district of each tree. The problem is, this information can’t be used as keys and values (why?). You will need to define a subclass of Writable to contain both information. The reducer should consolidate all this data and only output the district.

`
[thomas.almeida@bigdata01 ~]$ hdfs dfs -rm -r /user/thomas.almeida/output_oldestTreeDistrict
yarn jar /home/thomas.almeida/hadoop-examples-mapreduce-1.0-SNAPSHOT-jar-with-dependencies.jar oldestTreeDistrict /user/thomas.almeida/trees.csv /user/thomas.almeida/output_oldestTreeDistrict
hdfs dfs -cat /user/thomas.almeida/output_oldestTreeDistrict/part-r-00000
rm: `/user/thomas.almeida/output_oldestTreeDistrict': No such file or directory
24/07/15 11:48:24 INFO client.AHSProxy: Connecting to Application History server at bigdata02.efrei.hadoop.clemlab.io/62.210.145.80:10200       
24/07/15 11:48:24 INFO hdfs.DFSClient: Created token for thomas.almeida:
 HDFS_DELEGATION_TOKEN owner=thomas.almeida@EFREI.HADOOP.CLEMLAB.IO, ren
ewer=yarn, realUser=, issueDate=1721036904457, maxDate=1721641704457, sequenceNumber=1661, masterKeyId=22 on ha-hdfs:efrei
24/07/15 11:48:24 INFO kms.KMSClientProvider: New token created: (Kind: 
kms-dt, Service: kms://http@bigdata03.efrei.hadoop.clemlab.io:9292/kms, 
Ident: (kms-dt owner=thomas.almeida, renewer=yarn, realUser=, issueDate=
1721036904514, maxDate=1721641704514, sequenceNumber=1547, masterKeyId=8))
24/07/15 11:48:24 INFO security.TokenCache: Got dt for hdfs://efrei; Kin
d: HDFS_DELEGATION_TOKEN, Service: ha-hdfs:efrei, Ident: (token for thom
as.almeida: HDFS_DELEGATION_TOKEN owner=thomas.almeida@EFREI.HADOOP.CLEM
LAB.IO, renewer=yarn, realUser=, issueDate=1721036904457, maxDate=1721641704457, sequenceNumber=1661, masterKeyId=22)
24/07/15 11:48:24 INFO security.TokenCache: Got dt for hdfs://efrei; Kin
d: kms-dt, Service: kms://http@bigdata03.efrei.hadoop.clemlab.io:9292/km
s, Ident: (kms-dt owner=thomas.almeida, renewer=yarn, realUser=, issueDa
te=1721036904514, maxDate=1721641704514, sequenceNumber=1547, masterKeyId=8)
24/07/15 11:48:24 INFO mapreduce.JobResourceUploader: Disabling Erasure Coding for path: /user/thomas.almeida/.staging/job_1720701352744_0900   
24/07/15 11:48:24 INFO input.FileInputFormat: Total input files to process : 1
24/07/15 11:48:24 INFO mapreduce.JobSubmitter: number of splits:1
24/07/15 11:48:25 INFO mapreduce.JobSubmitter: Submitting tokens for job: job_1720701352744_0900
24/07/15 11:48:25 INFO mapreduce.JobSubmitter: Executing with tokens: [K
ind: kms-dt, Service: kms://http@bigdata03.efrei.hadoop.clemlab.io:9292/
kms, Ident: (kms-dt owner=thomas.almeida, renewer=yarn, realUser=, issue
Date=1721036904514, maxDate=1721641704514, sequenceNumber=1547, masterKe
yId=8), Kind: HDFS_DELEGATION_TOKEN, Service: ha-hdfs:efrei, Ident: (tok
en for thomas.almeida: HDFS_DELEGATION_TOKEN owner=thomas.almeida@EFREI.
HADOOP.CLEMLAB.IO, renewer=yarn, realUser=, issueDate=1721036904457, maxDate=1721641704457, sequenceNumber=1661, masterKeyId=22)]
24/07/15 11:48:25 INFO conf.Configuration: found resource resource-types.xml at file:/etc/hadoop/1.2.4.0-10/0/resource-types.xml
24/07/15 11:48:25 INFO impl.TimelineClientImpl: Timeline service address: bigdata02.efrei.hadoop.clemlab.io:8190
24/07/15 11:48:25 INFO impl.YarnClientImpl: Submitted application application_1720701352744_0900
24/07/15 11:48:25 INFO mapreduce.Job: The url to track the job: https://
bigdata01.efrei.hadoop.clemlab.io:8090/proxy/application_1720701352744_0900/
24/07/15 11:48:25 INFO mapreduce.Job: Running job: job_1720701352744_0900
24/07/15 11:48:31 INFO mapreduce.Job: Job job_1720701352744_0900 running in uber mode : false
24/07/15 11:48:31 INFO mapreduce.Job:  map 0% reduce 0%
24/07/15 11:48:37 INFO mapreduce.Job:  map 100% reduce 0%
24/07/15 11:48:43 INFO mapreduce.Job:  map 100% reduce 100%
24/07/15 11:48:43 INFO mapreduce.Job: Job job_1720701352744_0900 completed successfully
24/07/15 11:48:43 INFO mapreduce.Job: Counters: 54
        File System Counters
                FILE: Number of bytes read=1315
                FILE: Number of bytes written=615539
                FILE: Number of read operations=0
                FILE: Number of large read operations=0
                FILE: Number of write operations=0
                HDFS: Number of bytes read=16787
                HDFS: Number of bytes written=7
                HDFS: Number of read operations=8
                HDFS: Number of large read operations=0
                HDFS: Number of write operations=2
                HDFS: Number of bytes read erasure-coded=0
        Job Counters
                Launched map tasks=1
                Launched reduce tasks=1
                Data-local map tasks=1
                Total time spent by all maps in occupied slots (ms)=11349
                Total time spent by all reduces in occupied slots (ms)=15208
                Total time spent by all map tasks (ms)=3783
                Total time spent by all reduce tasks (ms)=3802
                Total vcore-milliseconds taken by all map tasks=3783    
                Total vcore-milliseconds taken by all reduce tasks=3802 
                Total megabyte-milliseconds taken by all map tasks=5810688
                Total megabyte-milliseconds taken by all reduce tasks=7786496
        Map-Reduce Framework
                Map input records=98
                Map output records=77
                Map output bytes=1155
                Map output materialized bytes=1315
                Input split bytes=107
                Combine input records=0
                Combine output records=0
                Reduce input groups=1
                Reduce shuffle bytes=1315
                Reduce input records=77
                Reduce output records=1
                Spilled Records=154
                Shuffled Maps =1
                Failed Shuffles=0
                Merged Map outputs=1
                GC time elapsed (ms)=64
                CPU time spent (ms)=1030
                Physical memory (bytes) snapshot=1530753024
                Virtual memory (bytes) snapshot=6698545152
                Total committed heap usage (bytes)=1524105216
                Peak Map Physical memory (bytes)=1196109824
                Peak Map Virtual memory (bytes)=3110989824
                Peak Reduce Physical memory (bytes)=334643200
                Peak Reduce Virtual memory (bytes)=3587555328
        Shuffle Errors
                BAD_ID=0
                CONNECTION=0
                IO_ERROR=0
                WRONG_LENGTH=0
                WRONG_MAP=0
                WRONG_REDUCE=0
        File Input Format Counters
                Bytes Read=16680
        File Output Format Counters
                Bytes Written=7
1601    5

`



### 1.8.7 District containing the most trees (very difficult)
Write a MapReduce job that displays the district that contains the most trees. The problem is that the program will almost certainly display a list of pairs (district number, number of trees) not ordered by number. If we apply this program to real big data not limited to the arrondissements of Paris, we would recover a huge list, unusable and the classification could take hours. How do you keep only the best answer? The solution probably goes through a second MapReduce phase, in which the Mapper retrieves the pairs (district, number) from the first phase, and makes them pairs whose key is unimportant (NullWritable) and the values themselves are the same input pairs. The Reducer receives them all and must keep the best pair.

`
[thomas.almeida@bigdata01 ~]$ hdfs dfs -rm -r /user/thomas.almeida/output_districtmaxtrees
yarn jar /home/thomas.almeida/hadoop-examples-mapreduce-1.0-SNAPSHOT-jar-with-dependencies.jar districtmaxtrees /user/thomas.almeida/trees.csv /user/thomas.almeida/output_districtmaxtrees
hdfs dfs -cat /user/thomas.almeida/output_districtmaxtrees/part-r-00000 
rm: `/user/thomas.almeida/output_districtmaxtrees': No such file or directory
24/07/15 11:48:59 INFO client.AHSProxy: Connecting to Application History server at bigdata02.efrei.hadoop.clemlab.io/62.210.145.80:10200       
24/07/15 11:48:59 INFO hdfs.DFSClient: Created token for thomas.almeida:
 HDFS_DELEGATION_TOKEN owner=thomas.almeida@EFREI.HADOOP.CLEMLAB.IO, ren
ewer=yarn, realUser=, issueDate=1721036939281, maxDate=1721641739281, sequenceNumber=1662, masterKeyId=22 on ha-hdfs:efrei
24/07/15 11:48:59 INFO kms.KMSClientProvider: New token created: (Kind: 
kms-dt, Service: kms://http@bigdata03.efrei.hadoop.clemlab.io:9292/kms, 
Ident: (kms-dt owner=thomas.almeida, renewer=yarn, realUser=, issueDate=
1721036939339, maxDate=1721641739339, sequenceNumber=1548, masterKeyId=8))
24/07/15 11:48:59 INFO security.TokenCache: Got dt for hdfs://efrei; Kin
d: HDFS_DELEGATION_TOKEN, Service: ha-hdfs:efrei, Ident: (token for thom
as.almeida: HDFS_DELEGATION_TOKEN owner=thomas.almeida@EFREI.HADOOP.CLEM
LAB.IO, renewer=yarn, realUser=, issueDate=1721036939281, maxDate=1721641739281, sequenceNumber=1662, masterKeyId=22)
24/07/15 11:48:59 INFO security.TokenCache: Got dt for hdfs://efrei; Kin
d: kms-dt, Service: kms://http@bigdata03.efrei.hadoop.clemlab.io:9292/km
s, Ident: (kms-dt owner=thomas.almeida, renewer=yarn, realUser=, issueDa
te=1721036939339, maxDate=1721641739339, sequenceNumber=1548, masterKeyId=8)
24/07/15 11:48:59 INFO mapreduce.JobResourceUploader: Disabling Erasure Coding for path: /user/thomas.almeida/.staging/job_1720701352744_0901   
24/07/15 11:48:59 INFO input.FileInputFormat: Total input files to process : 1
24/07/15 11:48:59 INFO mapreduce.JobSubmitter: number of splits:1       
24/07/15 11:48:59 INFO mapreduce.JobSubmitter: Submitting tokens for job: job_1720701352744_0901
24/07/15 11:48:59 INFO mapreduce.JobSubmitter: Executing with tokens: [K
ind: kms-dt, Service: kms://http@bigdata03.efrei.hadoop.clemlab.io:9292/
kms, Ident: (kms-dt owner=thomas.almeida, renewer=yarn, realUser=, issue
Date=1721036939339, maxDate=1721641739339, sequenceNumber=1548, masterKe
yId=8), Kind: HDFS_DELEGATION_TOKEN, Service: ha-hdfs:efrei, Ident: (token for thomas.almeida: HDFS_DELEGATION_TOKEN owner=thomas.almeida@EFREI.HADOOP.CLEMLAB.IO, renewer=yarn, realUser=, issueDate=1721036939281, maxDate=1721641739281, sequenceNumber=1662, masterKeyId=22)]
24/07/15 11:49:00 INFO conf.Configuration: found resource resource-types.xml at file:/etc/hadoop/1.2.4.0-10/0/resource-types.xml
24/07/15 11:49:00 INFO impl.TimelineClientImpl: Timeline service address: bigdata02.efrei.hadoop.clemlab.io:8190
24/07/15 11:49:00 INFO impl.YarnClientImpl: Submitted application application_1720701352744_0901
24/07/15 11:49:00 INFO mapreduce.Job: The url to track the job: https://bigdata01.efrei.hadoop.clemlab.io:8090/proxy/application_1720701352744_0901/    
24/07/15 11:49:00 INFO mapreduce.Job: Running job: job_1720701352744_0901
24/07/15 11:49:06 INFO mapreduce.Job: Job job_1720701352744_0901 running in uber mode : false
24/07/15 11:49:06 INFO mapreduce.Job:  map 0% reduce 0%
24/07/15 11:49:12 INFO mapreduce.Job:  map 100% reduce 0%
24/07/15 11:49:18 INFO mapreduce.Job:  map 100% reduce 100%
24/07/15 11:49:18 INFO mapreduce.Job: Job job_1720701352744_0901 completed successfully
24/07/15 11:49:18 INFO mapreduce.Job: Counters: 54
        File System Counters
                FILE: Number of bytes read=976
                FILE: Number of bytes written=614083
                FILE: Number of read operations=0
                FILE: Number of large read operations=0
                FILE: Number of write operations=0
                HDFS: Number of bytes read=16787
                HDFS: Number of bytes written=6
                HDFS: Number of read operations=8
                HDFS: Number of large read operations=0
                HDFS: Number of write operations=2
                HDFS: Number of bytes read erasure-coded=0
        Job Counters
                Launched map tasks=1
                Launched reduce tasks=1
                Data-local map tasks=1
                Total time spent by all maps in occupied slots (ms)=11514
                Total time spent by all reduces in occupied slots (ms)=15368
                Total time spent by all map tasks (ms)=3838
                Total time spent by all reduce tasks (ms)=3842
                Total vcore-milliseconds taken by all map tasks=3838
                Total vcore-milliseconds taken by all reduce tasks=3842
                Total megabyte-milliseconds taken by all map tasks=5895168
                Total megabyte-milliseconds taken by all reduce tasks=7868416
        Map-Reduce Framework
                Map input records=98
                Map output records=97
                Map output bytes=776
                Map output materialized bytes=976
                Input split bytes=107
                Combine input records=0
                Combine output records=0
                Reduce input groups=17
                Reduce shuffle bytes=976
                Reduce input records=97
                Reduce output records=1
                Spilled Records=194
                Shuffled Maps =1
                Failed Shuffles=0
                Merged Map outputs=1
                GC time elapsed (ms)=65
                CPU time spent (ms)=1050
                Physical memory (bytes) snapshot=1528958976
                Virtual memory (bytes) snapshot=6701146112
                Total committed heap usage (bytes)=1521483776
                Peak Map Physical memory (bytes)=1196818432
                Peak Map Virtual memory (bytes)=3111997440
                Peak Reduce Physical memory (bytes)=332140544
                Peak Reduce Virtual memory (bytes)=3589148672
        Shuffle Errors
                BAD_ID=0
                CONNECTION=0
                IO_ERROR=0
                WRONG_LENGTH=0
                WRONG_MAP=0
                WRONG_REDUCE=0
        File Input Format Counters
                Bytes Read=16680
        File Output Format Counters
                Bytes Written=6
16      36

`


