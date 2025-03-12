# HW4: Simple Movies Recommendation System
In this project, I implement a simple movies recommendation system.
There are two main tasks should be handled.

1. Each request contains a keyword and an user profile, the system should
    1. filter the movies by keywords
    2. do sorting via recommendation scores.
2. Handle multiple search requests simultaneously.

The dataset I used is [MovieLens](https://grouplens.org/datasets/movielens/),
you can go to the page if you want to get more information about it.

## Task 1: Filtering and Sorting

Each request contains a keyword, I first need to filter the movies containing the keyword.
Then I calculate recommendation scores for the filtered movies.

After calculating recommendation scores, I'm going to sort the movies by the scores.

I divide the list of the movies into several parts, delegate each part to a thread,
use the sorting library to sort each part, then merge them to get the final result.

There are two kinds of my merge sort:

1. multithread: tserver
2. multiprocess: pserver

The figure below shows the details of the sorting (with depth = 3).

![merge sort](https://i.imgur.com/RYEFMrq.png)

## Task 2: Handle Multiple Requests Simultaneously

In some test cases, they will include more than one request. You may need to use multithread to handle multiple requests simultaneously. It might not be possible to expect requests to be processed sequentially within the time limit.

You should be careful to deal with possible race problems when processing requests, since the requests are globally shared. You can use any method taught in this course to protect the shared resources, i.e., critical section, but we recommend you to use mutex since using signal may be more complicated.

## Sample Execution

In order not to let the test result of the running time of the program be affected by the current workload, we will run your program 3-5 times and take the test result with the shortest running time for each testcase. Meanwhile, we will check the consistency of your results among the tests. If the results are inconsistent, or once the program is crashed, then you will not get points of the testcase. 

Your `Makefile` should produce executable file `tserver` for using multithread to do merge sort  and `pserver` for using multiprocess to do merge sort. The output results `{}.out` of your program should place in your current working dir. TA will pull your repository and replace the `lib.c` library and run with following command to test your program in **linux1.csie.ntu.edu.tw**:

```
make 
./pserver < /path/to/input/data  
./tserver < /path/to/input/data
```

Remember `make clean` to remove all `{}.out` and executable file.


## Reference
* [Assignment](https://hackmd.io/@claire2222/SkLyBSnIo)
