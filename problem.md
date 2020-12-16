# deCODE it

In Computer science and Information theory, a [**Huffman code** ](https://en.wikipedia.org/wiki/Huffman_coding) is a particular type of optimal Prefix code that is commonly used for Lossless data compression. The process of finding or using such a code proceeds by means of Huffman coding.

Alice was once wondering if he could somehow find a way to decode the string. Bob, a master in Huffman code, gave him a task to solve. Bob told Alice that the frequency of characters and code word length is inversly related to each other. Moreover, all the edges contain a digit. Upon moving right from a node, the corresponding edge digit is a 1 and upon moving left from a node to its child node, the corresponding digit is a 0. Interestingly, the leaves of this Binary Tree contain a letter and it's frequency count. The non-leaf nodes would contain a NULL character instead of the letter and the frequency of all of it and it's successing characters.

While explaining further, Bob gave the example of SKILLENZAA. There are a total of **10** characters in the string. So, the root node has the frequency count as 10. Here, our frequencies are **A = 2 , E = 1,I = 1, K = 1, L = 2, N = 1, S = 1, Z = 1**. So, our Binary tree will have it's leaf nodes as these characters and their frequency counts. 
Similarly, Bob gave another example of the string... check the below image for the case **_ABRACADABRA_**.

![Explainination Binary Tree for ABRACADABRA](Images/explaination.png)

From the above Binary Tree, we can say that
> A - 0 
> B - 111
> C - 1100
> D - 1101
> R - 10

Hence, our Huffman Encoded string is
>  A \\ B  \\ R  \\ A \\ C \\ A \\ D \\ A \\ B \\ R \\ A
    0 \\ 111 \\ 10 \\ 0 \\ 1100 \\ 0 \\ 1101 \\ 0 \\ 111 \\ 10 0
or
01111001100011010111100

Bob further clarified to Alice that Huffman encoding is a prefix free encoding technique i.e. none of the obtained codeword is a prefix of any other codeword/

Alice now knows that he has to chase the 0s and 1s till he reaches a leaf to decode the string.

Bob gives Alice a pointer to the root of the Binary Huffman tree and a string consisting of only 0s and 1s. Help Alice to print the decoded string

# Function Description

Complete the function help_alice. It must return the decoded string.
help_alice has the following parameters : 

- root : **pointer** of type node*  to the root of Huffman Binary Tree
- s : Bob's encoded **string** through Huffman technique explained above

## Input Format
There is only one line : Bob's encoded **string**, s.

## Output Format

Ouptut Alice's decoded string on a single line. 
> **Note:** The background code takes care of creating the Binary Huffman Tree which then passes the root node and the string to the help_alice function
> 
## Constraints

1 $\leq$ |s| $\leq$ 100

## Sample Input

![Sample Input Binary Tree](Images/sample_input.png)
> s = "1001011"


## Sample Output

**ABACA**


# Explaination

s = "100101"
> s[0] = 1 : So move to the right child where we encounter a leaf with data as A. We return back to the root node. 
> s[1] = 0 : Hence we move to the left child from the root node.
> .
> .
> .
> Similarly we continue till s[6] = 1 : We move to the right child where we encounter a the data A.
> At the end, we obtain the string **"ABACA"**
