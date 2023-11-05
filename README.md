# OS-EX.6-IMPLEMENTATION-OF-INTER-PROCESS-COMMUNICATION-USING-PIPE

## AIM:

Write C programs to illustrate IPC using pipes mechanisms.

## ALGORITHM:
1. Create a child process usingfork()
2. Create a simple pipe with C, we make use of the pipe() systemcall.
3. Create two file descriptor fd[0] is set up for reading, fd[1] isset up forwriting
4. Close the read end of parent process using close() and perform writeoperation
5. Close the write end of child process and performreading
6. Display the text.

## PROGRAM:
```
DEVELOPED BY:A.J.PRANAV
REGISTER NO:212222230107
```
```
#include <stdio.h>
int main()
{
int fd[2],child; char a[10];
printf("\n Enter the string:");
scanf("%[^\n]",a);
pipe(fd);
child=fork();
if(!child)
{
close(fd[0]);
write(fd[1],a,5); wait(0);
}
else
{
close(fd[1]);
read(fd[0],a,5); printf("The string received from pipe is: %s",a);
}
return 0;
}
```
## OUTPUT:

![image](https://github.com/Pranav-AJ/OS-EX.6-IMPLEMENTATION-OF-INTER-PROCESS-COMMUNICATION-USING-PIPE/assets/118904526/23f27ea4-73ab-47f4-9325-d3245c8217aa)

## RESULT:

Thus, IPC using pipes mechanisms is illustrated using c program successfully.
