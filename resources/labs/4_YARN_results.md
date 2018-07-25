# Lab 7 Yarn result tests
```
< lowest >
Testing loop started on Wed Jul 25 00:00:23 UTC 2018
MAPPER CONTAINNERS: 2
REDUCER CONTAINNERS: 8
MAPPER HEAP : 3276
REDUCER HEAP : 3276
STARTING TERAGEN

real    0m22.267s
user    0m15.039s
sys     0m0.954s
STARTING TERASORT

real    0m57.387s
user    0m49.946s
sys     0m4.367s
Deleted /results/tg-10GB-2-8-4096
Deleted /results/ts-10GB-2-8-4096
Starting new test
MAPPER CONTAINNERS: 2
REDUCER CONTAINNERS: 8
MAPPER HEAP : 6553
REDUCER HEAP : 6553
STARTING TERAGEN

real    0m22.220s
user    0m15.017s
sys     0m0.884s
STARTING TERASORT

real    0m58.206s
user    0m49.425s
sys     0m4.461s
Deleted /results/tg-10GB-2-8-8192
Deleted /results/ts-10GB-2-8-8192
Starting new test
Testing loop ended on Wed Jul 25 00:03:13 UTC 2018
```

```
< fastest >
Testing loop started on Wed Jul 25 00:05:14 UTC 2018
MAPPER CONTAINNERS: 8
REDUCER CONTAINNERS: 2
MAPPER HEAP : 3276
REDUCER HEAP : 3276
STARTING TERAGEN

real    0m22.369s
user    0m15.133s
sys     0m1.080s
STARTING TERASORT

real    0m51.175s
user    0m45.495s
sys     0m4.223s
Deleted /results/tg-10GB-8-2-4096
Deleted /results/ts-10GB-8-2-4096
Starting new test
MAPPER CONTAINNERS: 8
REDUCER CONTAINNERS: 2
MAPPER HEAP : 6553
REDUCER HEAP : 6553
STARTING TERAGEN

real    0m24.963s
user    0m14.412s
sys     0m0.959s
STARTING TERASORT

real    0m56.479s
user    0m46.087s
sys     0m4.262s
Deleted /results/tg-10GB-8-2-8192
Deleted /results/ts-10GB-8-2-8192
Starting new test
Testing loop ended on Wed Jul 25 00:07:59 UTC 2018

```