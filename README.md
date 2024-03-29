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
```c
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

## OUTPUT

![image](https://github.com/Madhavareddy09/Linux-Process-API-fork-wait-exec/assets/145742470/5a896dff-d4b2-4e4b-9e24-0e43b6962a8a)



## C Program to create new process using Linux API system calls fork() and exit()
```c
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


## OUTPUT


![image](https://github.com/Madhavareddy09/Linux-Process-API-fork-wait-exec/assets/145742470/ea2d94d8-bce7-4d6f-a6bf-314fc44fff42)



## C Program to execute Linux system commands using Linux API system calls exec() family
```c
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


## OUTPUT


![image](https://github.com/Madhavareddy09/Linux-Process-API-fork-wait-exec/assets/145742470/223f9394-39ec-4dc0-a9ec-dc25ec4f261e)



### Developed by : K MADHAVA REDDY 
### Register Number : 212223240064


# RESULT:
The programs are executed successfully.
