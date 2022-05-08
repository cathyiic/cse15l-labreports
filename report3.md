# Here are all of the implementations from Lab 5

**Streamlining ssh Configuration**


Here is my .ssh/config file that I created inside of the file, ednafiles, that we worked on during the last lab. ![](sshconfig.png)
In addition, I copied this config file using the `cp` command to copy it to `.ssh/config`.

Here is where I used the ssh command to log into my CSE15L account with my alias. Since I had created the **config** file and written all of my account login info, I can just call `ssh ieng6` to log into my cse15l account. ![](ssh ieng6.png)

Here is also another instance where I use the `scp` command to copy the `MarkdownParse.java` from my remote server onto my cse15l account. First, I exit my ieng6 account and went back to my remote server. I ran the `scp MarkdownParse.java ieng6:~/MarkdownParse.java` in my terminal. That copied it over. Then, I logged back into my ieng6 account and called `ls` to check if it copied over and it did!! ![](copied markdownparse.png)
