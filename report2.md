# Here is the Lab Report 2 Week 4

**Three Code Changes That My Lab Group Worked On**

-**1.** One of the first issues that all of my members ran into when we working on Lab 3 was that the MarkdownParse class was throwing an IndexOutOfBounds exception or running an infinite loop when we were testing the [test-file.md](https://github.com/cathyiic/cse15l-labreports/blob/main/test-file.md) file. We consulted one of the tutors on this, and she instructed us that the code we wrote for the MarkdownParse class.

```
public class MarkdownParse {
    public static ArrayList<String> getLinks(String markdown) {
        ArrayList<String> toReturn = new ArrayList<>();
        // find the next [, then find the ], then find the (, then read link upto next )
        int currentIndex = 0;
        while(currentIndex < markdown.length()) {
            System.out.println(currentIndex);
            int openBracket = markdown.indexOf("[", currentIndex);
            int closeBracket = markdown.indexOf("]", openBracket);
            int openParen = markdown.indexOf("(", currentIndex);
            int closeParen = markdown.indexOf(")", openParen);
            toReturn.add(markdown.substring(openParen + 1, closeParen));
            currentIndex = closeParen + 1;
            System.out.println(currentIndex); //prints the output
        }

        return toReturn;
    }
    public static void main(String[] args) throws IOException {
        Path fileName = Path.of(args[0]);
        String content = Files.readString(fileName);
        ArrayList<String> links = getLinks(content);
	    System.out.println(links);
    }
}
```

The issues here was that the code for the MarkdownParse class is faulty, so if our test file ended with an empty line, it would throw an IndexOutOfBounds exception. Therefore, we had to change our test file to make sure that none of our test files ended with an empty line to avoid this bug from happening again. The bug in our code in MarkdownParse class doesn't consider the extra line at the end, so tthat bug is what essentially threw this error. The symptom of the error happens from this bug from our failure-induced input of having that extra line.
Here is a screenshot of where the empty line in the test file was deleted in order to avoid the IndexOutOfBounds exception from my Github commit history.
![](space.png)
Here is also the output symptom of that failure-inducing input that occurs when there is an empty extra line in our test file. 
![](index out of bounds.png)
Therefore, we had to make modification of deleting the empty last line to fix this failure-induced bug.

-**2.** Another code change that we made was if the test file, breaking.md, had an open parentheses. When linking the link in my breaking.md file, [](https://github.com/cathyiic/cse15l-labreports/blob/main/breaking%201.png) there was an open parentheses for 

```[TWITTER](https://twitter.com```

My group and I fixed this mistake by adding the parentheses at the end of the line. The bug also lies within our code, because it only will run correcly if it seaches the test file and finds the conditional of both the open and close parentheses&/brackets. The symptom was it throwing the ArrayIndexOutOfBounds exception from the failure-induced test file we ran through the code. 
This fixed this symptom errror by adding the parentheses at the end of the line to ensure that our code from the MarkdownParse class will correctly run.
![](breaking 1.png)
Without fixing the bug, the test file would output an ArrayIndexOutOfBounds exception for us. Here is a screenshot of what the symptom would look like with the failure-inducing input. 
![](no paren.png)

-**3.** Another code change that my group and I made to a test file, [breaking2.md](https://github.com/cathyiic/cse15l-labreports/blob/main/breaking%202.md), was adding a bracket to the end of the file name, since the bracket was not closed. The bug once again was because of the code in the MarkdownParse class searching for both the open & close brackets. Since we have the failure-induced input in our breaking2.md file, we get the symptom of getting an error message when we try to run our code. This failure-inducing input causes this error to output this error into our terminal. Our code throws an ArrayIndexOutOfBounds exception for this as well. 
Here is a screenshot of the commit changes that were made to our file to get rid of the symptom. 
![](fixed bracket.png)
Without fixing the bug, the test file would output an ArrayIndexOutOfBounds exception for us. Here is a screenshot of what the symptom would look like with the failure-inducing input. Here is a screenshot of what the symptom would look like with the failure-inducing input. 
![](breaking 2.png)

