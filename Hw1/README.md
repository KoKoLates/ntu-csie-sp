# HW1: Booking
The system is comprised of read servers and write servers. Both can access a file `bookingRecord` that records information about users’ bookings. When a server gets a request from a client, it will respond according to the file’s content. A read server tells the client how many items it has booked. A write server can modify the file to book more or less items.

## Sample Judge
In addtion to testing your server with `read_server`, `write_server` and `telnet`, we provide [`sample_judge.py`](./sample_judge.py) and a bookingRecord so that you can test your program with a single command.

### Arguments
`sample_judge.py` accepts following optional arguments:

* `-v`, `--verbose`: verbose. if you set this argument, `sample_judge.py` will print messages delivered between server and client, which may help debugging.
* `-t TASK [TASK ...]`, `--task TASK [TASK ...]`, Specify which tasks you want to run. If you didn't set this argument, `sample_judge.py` will run all tasks by default.
    * Valid `TASK` are `["1_1", "1_2", "2", "3", "4", "5_1", "5_2"]`.

For example, 
```python
python sample_judge.py -t 1_1 3 5_1 -v 
```
set sample_judge.py to be verbose, and runs only task 1-1, task 3 and task 5-1.

### Notice on Sample Judge
Score printed by `sample_judge.py` is just for your reference. Real judge is much more complicated than `sample_judge.py.` Besides, autograding also used `sample_judge.py` for scoring.

## Reference
* [Assignment](https://hackmd.io/@GTooth/By12six1j)
