# htc-wordcount
A simple wordcount job for running on CHTC's High Throughput Computing system.

### Requirements

Execution Points must have Python 3.

## Submit the job

1. Clone the git repo while logged into the Access Point. The `[user@ap2002]$` represents the Access Point terminal. **Do not copy this part of the code block.**
    ```
    [user@ap2002]$ git clone https://github.com/xamberl/htc-wordcount.git
    ```
    
1. Change into the `htc-wordcount` directory.
    ```
    [user@ap2002]$ cd htc-wordcount
    ```
    
1. *Optional*: Test the `wordcount.py` script to understand its behavior.
    ```
    [user@ap2002]$ ./wordcount.py Dracula.txt
    ```
   
1. View the contents of the submit file `wordcount.sub`. This file describes the computational work we want to  submit to HTCondor.
    ```
    [user@ap2002]$ cat wordcount.sub
    ```
    
1. Submit the job.
    ```
    [user@ap2002]$ condor_submit wordcount.sub
    ```
    
1. To query the status of the job, use the `condor_q` command.
    ```
    [user@ap2002]$ condor_q
    ```
    Alternatively, you can watch the status of your job in real time using `condor_watch_q`. To exit this utility and return to your terminal, press `CTRL`+`C`.
    ```
    [user@ap2002]$ condor_watch_q
    ```
    
1. When the job is complete, you should see new files in your directory using the `ls` command.
    ```
    [user@ap2002]$ ls
    ```
    Print the output of the `job_*.out` file to see our expected output!
   ```
   [user@ap2002]$ cat job_*.out
   ```
