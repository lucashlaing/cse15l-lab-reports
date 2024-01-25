# Lab Report 1


## `cd` with no arguments
![Image](CdNoArg.png)


The working directory was `/home/lecture1/messages` when the code was run. `cd` does not have any output and it worked as expected. As there was no argument, our directory went back to the root directory which is  `/home`. There was no output as  `cd` never gives an output and only changes our directory.


## `cd` with directory as argument
![Image](CdArgDirect.png)


The working directory was `/home` when the code was run. `cd` does not have any output and it worked as expected. We changed our working directory to `/home/lecture1` and we can see this in the next line. The output is not an error since we switched directories like we wanted.


## `cd` with file as argument
![Image](CdArgFile.png)


The working directory was `/home/lecture1` when the code was run. `cd` gave an error output as the code did not work as expected. We could not change our directory to `Hello.java` because it is a file and not a folder/directory.


## `ls` with no argument
![Image](LsNoArg.png)


The working directory was `/home/lecture1` when the code was run. `ls` gave an output of all the files and folders that are inside the `lecture1` folder. Having no arguments meant that we wanted to know all the files and folders in the current directory. There were no errors.


## `ls` with directory as argument
![Image](LsArgDirect.png)


The working directory was `/home/lecture1` when the code was run. `ls` gave an output of all the files that were inside the `messages` folder. As we passed in the `messages` path as an arugment, `ls` showed all the files inside of it. There were no errors.


## `ls` with file as argument
![Image](LsArgFile.png)


The working directory was `/home/lecture1` when the code was run.`ls` returned the name of the file we passed in as an argument, which was `Hello.java`. There were no errors but this was pointless as we did not find out what was inside the file. 


## `cat` with no argument
![Image](CatNoArg.png)


The working directory was `/home/lecture1` when the code was run. `cat` did not print any output unless something else was typed into the terminal. It would then output exactly what you would type into it. Looking into cat without an argument, I realized that some developers use it to get rid of any formatting done to text. Some more research also tells me that it was more useful in the past with the first computers. I had to press `Crtl + c` to escape from this, which terminated the program. 


## `cat` with directory as argument
![Image](CatArgDirect.png)


The working directory was `/home/lecture1` when the code was run. `cat` gave an error as an output stating that `messages` was a directory. `cat` could not print the contents since `messages` is not a file. 


## `cat` with file as argument
![Image](CatArgFile.png)


The working directory was `/home/lecture1/messages` when the code was run. `cat` printed "Hello World!" as that was the contents of the file that we passed into it. 
