# hashstress

A script for multithreaded stress test of I/O, cache and processing correctness using hash calculations

Read more: https://larsee.com/blog/tag/hashstress.html

`hashstress` is a script for stressing and testing the correctness of disk I/O, cache, memory and processing subsystems for an extended period of time. The basic idea is to generate files with random content and repeatedly calculate hash checksums verifying that they are the same every time. 

The script can be configured with the size of dataset, number of threads, type of hash-function and number of repetitions. 

## Example run

Download the script and make it executable:

```text
$ git clone https://github.com/larspontoppidan/hashstress.git
$ cd hashstress
$ chmod +x hashstress
$ ./hashstress 
hashstress rev. 2018-06-17, see more: http://larsee.com/blog/tag/hashstress

Syntax: ./hashstress <size pr. thread> <threads> <repetitions> <hash-cmd>

Example: ./hashstress 1G 4 20 md5sum
```

The following test will generate a dataset of 4 GB and have four threads running md5sum calculations 20 times:

```text
$ ./hashstress 1G 4 20 md5sum
hashstress rev. 2018-06-17, see more: http://larsee.com/blog/tag/hashstress
Test config:
 - Data set: 4 file(s) each 1G
 - Threads: 4, repetitions: 20
 - Hash command: md5sum

Start time: Sun Jun 17 17:38:31 EEST 2018
Generating random data file(s) ...
Generating reference checksum(s) ...
Repetition: 1 2 3 4 5 6 7 8 9 10 11 12 13 14 15 16 17 18 19 20
Cleaning up
Repetitions took: 42 seconds
Test result: PASS
```

