# Hash Hash Hash
Hash Hash Has is a lab that utilizes mutex locks that safely runs concurrent threads
when initializing a hash table. We will use different implementations that allow for varying amounts of performance

## Building
```shell
make
```

## Running
```shell
./hash-table-tester -t [#ofthreads] -s [#ofentries]
```
An example would be:
```shell
./hash-table-tester -t 4 -s 10000
```
## First Implementation
In the `hash_table_v1_add_entry` function, I added a mutex to the entire structure of the hash table. It is initialized during the create function and destroyed during the destroy function. The mutex locks the critical section which is where the process looks for entries and unlocks before it returns. This will ensure that only one thread will be able to go through the hash table at once, effectively making only one process be used which is why it will be slower than the base case.

### Performance
```shell
./hash-table-tester
```
Results:
Generation: 18,574 usec
Hash table base: 52,447 usec
  - 0 missing
Hash table v1: 88,868 usec
  - 0 missing
Version 1 is a little slower than the base version. As there is no parallelism because of the locks.

## Second Implementation
In the `hash_table_v2_add_entry` function, I TODO

### Performance
```shell
./hash-table-tester
```
TODO more results, speedup measurement, and analysis on v2

## Cleaning up
```shell
nake clean
```