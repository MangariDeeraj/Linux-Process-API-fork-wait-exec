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
#include <sys/types.h>
#include <unistd.h>
int main(void)
{	//variable to store calling function's process id
	pid_t process_id;
	//variable to store parent function's process id
	pid_t p_process_id;
	//getpid() - will return process id of calling function
	process_id = getpid();
	//getppid() - will return process id of parent function
	p_process_id = getppid();
	//printing the process ids

//printing the process ids
	printf("The process id: %d\n",process_id);
	printf("The process id of parent function: %d\n",p_process_id);
	return 0; }
```

##OUTPUT

![368435119-429ca3a8-b839-436c-afc3-448b13c27ffc](https://github.com/user-attachments/assets/5e7bd0ed-d048-4f73-b8fc-316939328a6b)


## C Program to create new process using Linux API system calls fork() and exit()
```
#include <stdio.h>
#include<stdlib.h>
int main()
{ int pid; 
pid=fork(); 
if(pid == 0) 
{ printf("Iam child my pid is %d\n",getpid()); 
printf("My parent pid is:%d\n",getppid()); 
exit(0); } 
else{ 
printf("I am parent, my pid is %d\n",getpid()); 
sleep(100); 
exit(0);} 
}
```

##OUTPUT

![368435489-3a63264d-a7dc-442e-bef7-0d7183fc433d](https://github.com/user-attachments/assets/7cb116b8-0878-407c-a5d4-e7ee7362e97c)


## C Program to execute Linux system commands using Linux API system calls exec() family
```
#include <unistd.h>
#include <stdio.h>
#include <stdlib.h>
int main()
{
	printf("Running ps with execlp\n");
	execlp("ps", "ps", "ax", NULL);
	printf("Done.\n");
	exit(0);
}
```
##OUTPUT

![368435820-6df70b75-cfe4-4f54-bdba-351b8ccfd495](https://github.com/user-attachments/assets/e6d62a8a-aa85-4441-8bb8-21d3c0109967)


# RESULT:
The programs are executed successfully.
