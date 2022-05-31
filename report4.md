# Here are the testings and implementations that were made in Week 7
The code was worked on with my lab partners and I. We worked on the implementations and the creation of the markdownparse class, which we all collaborated on Edna's Repo. Therefore, it is cloned from ednafiles, the repo we all worked on together. I have copied down the code from Edna's repo since we all worked on her repo rather than our own individual repos. 

Here is the link to my markdownparse [repo](https://github.com/cathyiic/markdown-parser-main-2/tree/main)

Here is the link to Edna's markdownparse [repo](https://github.com/ednavho/ednafiles) 

Here is the link to my peer's [repo](https://github.com/BellaReal/markdown-parser) 


**Testing for the first snippet**

1.

The expected output should be 
`` 
`[google.com, google.com, ucsd.edu]
``

2.

![](snippet1.png)

Here is the test that I made for the first snippet.

![](test1.png)

3.

Here is what the test outputs with my code.

![](output1.png)
4. The test did not pass, and JUnit tells us that ucsd.edu wasn't added and url.com is at the front of the list.

5.

Here is running my peer's and their output.

![](bella1.png)


**Testing for the second snippet**

1.

The expected output should be 
``
`[a.com, a.com(()), example.com]
``

2.

![](snippet2.png)

Here is the test that I made for the second snippet.

3.

![](test2.png)

Here is what the test outputs with my code.

![](output2.png)
4. The test did not pass, and JUnit tells us that the nested parenthesis wasn't added and example.com wasn't included at the end of the list.

5.

Here is running my peer's and their output.

![](bella2.png)


**Testing for the third snippet**

1.

The expected output should be 
``
`[https://sites.google.com/eng.ucsd.edu/cse-15l-spring-2022/schedule]
``

2.

![](snippet3.png)

Here is the test that I made for the third snippet.

3.

![](test3.png)

Here is what the test outputs with my code.

![](output3.png)
4. The test did not pass, and JUnit tells us that an assertion error was thrown because `links` and `content` were not equal to each other.

5.

Here is running my peer's and their output.

![](bella3.png)


**Answering Some of the Questions**

1. *Do you think there is a small (<10 lines) code change that will make your program work for snippet 1 and all related cases that use inline code with backticks? If yes, describe the code change. If not, describe why it would be a more involved change.*
**Yes, I believe that there can be a small code change (in <10 lines) for snippet 1. The code will check for parenthesis and brackets, so after it does so, the code should also check for the ticks and those inside of the brackets. Another part that can be changed in the code is that it can also look to see if there's any additional closed brackets after a tick or another closed bracket, as we see in the last line of snippet 1.**

2. *Do you think there is a small (<10 lines) code change that will make your program work for snippet 2 and all related cases that nest parentheses, brackets, and escaped brackets? If yes, describe the code change. If not, describe why it would be a more involved change.*
**Yes, I believe that there can be a small code change (in <10 lines) for snippet 2. As we see in line 2 of the snippet 2, it should take into consideration any nested punctuation that is happening. That means that the program should check for duplicates and count the pairs of open and closed parentheses to match them up. I think that an even easier fix to this bug is that the program can ignore the nesting, since the nesting isn't important when formatting and focus only on the outside parentheses.**

3. *Do you think there is a small (<10 lines) code change that will make your program work for snippet 3 and all related cases that have newlines in brackets and parentheses? If yes, describe the code change. If not, describe why it would be a more involved change.*
**Yes, I believe that there can be a small code change (in <10 lines) for snippet 3. Before the issue with the code was that it was not taking into account the spaces or empty lines at the end of the file. However, with snippet 3, I think that there is a problem with the large amount of empty spaces in between the text that is because of the line breaks. I think that the code can look at the line breaks and ignore the weird line break formatting but search for the beginning and end of the brackets and the beginning and end of the parentheses.**




