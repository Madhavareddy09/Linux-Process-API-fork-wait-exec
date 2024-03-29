# Linux-Process-API-fork-wait-exec-
Ex02-Linux Process API-fork(), wait(), exec()
# Ex02-OS-Linux-Process API - fork(), wait(), exec()
Operating systems Lab exercise


# AIM:
To write C Program that uses Linux Process API - fork(), wait(), exec()

# DESIGN STEPS:

### Step 1:

Navigate to any Linux environment installed on the system or installed inside a virtual environment like virtual box/vmware or online linux JSLinux (https://bellard.org/jslinux/vm.html?url=alpine-x86.cfg&mem=192) or docker.

### Step 2:

Write the C Program using Linux Process API - fork(), wait(), exec()

### Step 3:

Test the C Program for the desired output. 

# PROGRAM:

## C Program to print process ID and parent Process ID using Linux API system calls
```
#include <stdio.h>
#include <unistd.h>

int main() {
    pid_t pid, parent_pid;

    pid = getpid();

    parent_pid = getppid();

    printf("Process ID: %d\n", pid);
    printf("Parent Process ID: %d\n", parent_pid);

    return 0;
}

```















##OUTPUT
![image](https://github.com/Madhavareddy09/Linux-Process-API-fork-wait-exec/assets/145742470/16e07920-9097-42ac-b6f3-4668565e82dd)














## C Program to create new process using Linux API system calls fork() and exit()
```
#include <stdio.h>
#include <stdlib.h>
#include <unistd.h>
#include <sys/wait.h>

int main() {
    pid_t pid = fork();

    if (pid == -1) {
        perror("fork");
        exit(EXIT_FAILURE);
    }

    if (pid == 0) {
        // Child process
        printf("Child Process: PID = %d, Parent PID = %d\n", getpid(), getppid());
        exit(EXIT_SUCCESS);
    } else {
        // Parent process
        printf("Parent Process: PID = %d\n", getpid());
        wait(NULL);
    }

    return 0;
}

```












##OUTPUT

![image](https://github.com/Madhavareddy09/Linux-Process-API-fork-wait-exec/assets/145742470/8d9a7025-46f8-4f76-a81c-b53253f45146)







## C Program to execute Linux system commands using Linux API system calls exec() family
```
#include <stdio.h>
#include <stdlib.h>
#include <unistd.h>

int main() {
    printf("Executing ls command:\n");
    execl("/bin/ls", "ls", "-l", NULL);
    perror("execl");
    return 0;
}
```

























##OUTPUT
![image](https://github.com/Madhavareddy09/Linux-Process-API-fork-wait-exec/assets/145742470/b1bbdec2-12b6-4cd7-93f5-5658a798673d)















### Developed by : K MADHAVA REDDY 
### Register Number : 212223240064


# RESULT:
The programs are executed successfully.
