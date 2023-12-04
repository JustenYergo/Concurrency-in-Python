# Experimental Results

## Gather Data
* After running each version of the program, namely _Sequential_, _Threaded_ and _Process_, we collect runtimes and
store those in the following table, for posterior discussion. 

| Program Type  | Many Small Files | Few Large Files |
|---------------|-----------------:|----------------:|
| Sequential    |            0.462 |          38.320 |
| Thread-based  |            0.540 |          39.730 |
| Process-based |           14.708 |          13.652 |
| Shared_based  |            0.470 |          38.544 |

 
## Discussion
* Discuss with your team these questions:

**A) Did the Multi-threaded program (thread-based) improve the performance of the processing?** 

*If yes, explain why? If no, explain what do you think is the cause of that behavior*

*Your Answer here*

_ 

_No, there was no improvement in performance in the Multi-threaded program because
the GIL lock prevents any two threads from doing work at the exact same time.

_


**B) Did the Multi-Processing program (process-based) improve the performance of the processing?** 

*If yes, explain why? If no, explain what do you think is the cause of that behavior*

*Your Answer here*

_ 

_Yes, the Multi-Processing did improve the performance for the processing of a few large files.
I think that creating processes for all the small files took extra time, but for the few large
files the performance is improved because each process will run in a separate core, with its own Python
interpreter which mitigates the GIL lock.

_


**C) Which are the tradeoffs of achieving better performance?** 

*Your Answer here*

_

_The tradeoffs for Multi-Processing is that communication between processes is expensive
and creating processes takes a nonzero amount of time.

_
