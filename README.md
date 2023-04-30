Download Link: https://assignmentchef.com/product/solved-cs-251-project-4-sorting-and-trees
<br>
<h1>Part 1: Words Rhyme Sorting and Suffix Sharing (50 Points)</h1>

In this part, you are going to implement the QuickSort algorithm and use it to sort words based on rhyme (i.e., the correspondence of sound between the endings of words). In addition, you will then group the words that share suffixes (e.g., the two words “Sort<strong>ing</strong>​ ”​ and “Shar<strong>ing</strong>​ ”​ share the three-character suffix: “-​<strong>ing</strong>​”). Given a list of words, you are required to provide the following two operations:




<ul>

 <li><strong><u>Rhyme Operation : Sort all words in a rhyming order (25 points):</u></strong></li>

</ul>

To accomplish this task you need to apply the following steps:

<ol>

 <li>Read the input list of words into an array of strings.</li>

 <li>Reverse the letters in each word (e.g., “confound” becomes “dnuofnoc”). Capitalization does not matter.</li>

 <li>Sort the resulting array of words using your own implementation of QuickSort.</li>

 <li>Reverse the letters in each word back to their original state.</li>

 <li>Print the words to the output file.</li>

</ol>




<strong><u>Example 1: Rhyming Order:</u></strong>

Given the list of words: “compound”, “crabbit”, “confound”, “flashpit”, “astound”, and “trampit” The correct rhyming order of these words is: confound – compound – astound – crabbit – flashpit – trampit




<ul>

 <li><strong><u>Suffix Sharing Operation (25 points):</u></strong></li>

</ul>

For this operation, you need to Identify the suffixes which have at least <em>k</em>​ words ending with it (i.e., where ​<em>k </em>​is an input argument). You will group words based on suffix sharing. You need to make use of use of the rhyme order computed previously in this operation. This will enable you to implement this operation efficiently without the need to do a brute force check.




<strong><u>Example 2: Suffix Sharing (k=2)</u></strong>

Given: “rabbit”, “crabbit”, “flashpit”, “trampit” and k=2, will yield the following suffixes:  <strong>t</strong>​ – crabbit, flashpit, rabbit, trampit <strong>it</strong>​ – crabbit, flashpit, rabbit, trampit <strong>bit</strong>​ – crabbit, rabbit <strong>pit</strong>​ – flashpit, trampit <strong>bbit </strong>​- crabbit, rabbit <strong>abbit </strong>​- crabbit, rabbit

<strong>rabbit </strong>​- crabbit, rabbit




Note that if k=3 for the same list of words, output would be:

<strong>t</strong>​ – crabbit, flashpit, rabbit, trampit

<strong>it</strong>​ – crabbit, flashpit, rabbit, trampit

<strong> </strong>

<strong>Implementation instructions:</strong>

For both operations, you will need to apply the sorting on the reversed version of the words (i.e., for the word: “astound” -&gt; “dnuotsa”). You may implement this reverse function or use the string library for C++ or Java. However, you need to provide a full implementation of the QuickSort algorithm, which should work in-place.




In your implementation of the QuickSort, you do not necessarily need to implement string comparing functions, You can use strcmp functions in C++. Also, in Java, just make sure you implements the Comparator interface, so that you can use the (&lt;,&gt;) operators against strings. For the Suffix share implementation, you may want to use a hashmap to store the word lists associated with each suffix. Feel free to use the data structure that comes with the language library (C++ or Java). The test cases will measure the correctness and performance of your implementation using different input sequences.




<strong><u>Sample Input/output format:</u> </strong>

<ul>

 <li>The first integer is a 1 or a 2 indicating this is the input file for part 1 or 2, respectively;</li>

 <li>If it is part 1, second line integer implies required operation 1: rhyme or 2: suffix</li>

 <li>If it is rhyme operation: Third line integer implies that there are n lines following (i.e., n words).</li>

 <li>If it is suffix operation: Third line integer implies ​<em>k</em>​ and then the fourth line integer implies that there are n lines following (i.e., n words). ● After that, each line will have one word.</li>

</ul>

<strong> </strong>

<strong><u>Test Cases:</u> </strong>

Separate test cases will be given for the two operations and you will be graded independently. For example, if you only complete the Rhyme order, you will get 25pts.

<strong> </strong>

<table width="624">

 <tbody>

  <tr>

   <td width="312"><strong>Sample Input for operation 1: RhymeOrder </strong></td>

   <td width="312"><strong>Sample Output </strong></td>

  </tr>

  <tr>

   <td width="312">116compoundcrabbit confound flashpit astound trampit</td>

   <td width="312">confound compound astound crabbit flashpittrampit<strong> </strong></td>

  </tr>

  <tr>

   <td width="312"><strong>Sample Input for operation 2: SuffixShare </strong></td>

   <td width="312"><strong>Sample Output </strong></td>

  </tr>

  <tr>

   <td width="312">123 4 rabbit crabbit flashpit trampit <strong> </strong></td>

   <td width="312"><strong>t</strong>​ -&gt; [crabbit, flashpit, rabbit, trampit] <strong>it</strong>​ -&gt; [crabbit, flashpit, rabbit, trampit]</td>

  </tr>

 </tbody>

</table>

<strong> </strong>




<strong> </strong>

<strong>           </strong>

<h1>Part 2: Binary Search Tree (BST) (50 Points)</h1>




A Binary Search Tree (BST) is a tree data structure in which each node has at most two children, which are referred to as the left child and the right child and the topmost node in the tree is called the root. It additionally satisfies the binary search property, which states that the key in each node must be greater than or equal to any key stored in the left sub-tree, and less than to any key stored in the right subtree.







For this project, you can assume ​<strong>keys and values</strong>​ are the ​<strong>same </strong>​(so maintaining the key is enough). The keys will be ​<strong>integers and unique. </strong>​You are required to complete the following tasks.




<strong><u>Basic Operation: (10 pts)</u> </strong>

<ol>

 <li><strong>Insert a key into BST:</strong>​ ​insertKey(int key)-​  A new key is always inserted at a leaf. We start searching for a key from the root until we hit a leaf node. Once a leaf node is found, the new node is added as a child of the leaf node.</li>

</ol>




<ol start="2">

 <li><strong>Delete a key: </strong>​deleteKey (int key)- ​Remove the key node from the tree. If the key is not in the tree, do nothing.</li>

</ol>




<ol start="3">

 <li><strong>Search a key: </strong>​ searchKey(int key)​<strong> – </strong>​Search for the key in the BST; return true if found, return false otherwise. This function will be used by you elsewhere.</li>

</ol>




<ol start="4">

 <li><strong>Range Sum: </strong>​ rangeSum(int left, int right)- ​Return the summation of all</li>

</ol>

the keys in the BST falls in the range ​[left, right] ​inclusive. ​ ​For example, in the above case, the ​rangeSum(11,17) will return ​    ​26 [12 14]. ​Print “none” to file if no elements found.

55

<ol start="5">

 <li><strong>Height of a node: </strong>​int height(int key)​<strong> – </strong>​find and print the height of a node in BST. If a node with the key is not found, print “none” to file. For example, the 14 node in the tree above has height 3.</li>

</ol>




<strong>             </strong>

<strong><u>Traversal:  (10pts)</u> </strong>

<strong> </strong>

<strong> </strong>

<ol start="6">

 <li><strong>Postorder Traversal Print :</strong> – ​ ​postorder()​ –  get the Postorder traversal of the BST. For the above figure, Postorder (Left, Right, Root) should print “4 12 8 22 20”.</li>

</ol>




<ol start="7">

 <li><strong>Level Order Traversal Print :</strong>​ – ​levelorder()​ – get the Breadth First or Level order traversal of the BST. For the above figure, Breadth First or Level Order Traversal should print “20 8 22 4 12”. One way to implement level order is to use a queue. For all of the above traversal, print “none” in file if no elements present in tree.</li>

</ol>







<strong><u>Problem:  (15pts)</u> </strong>

<strong> </strong>

<ol start="8">

 <li><strong>Finding the lowest common ancestor (LCA) between two nodes in BST:</strong></li>

</ol>

int LCA(int key1, int key2)




Let T be a rooted tree. The lowest common ancestor between two nodes n1 and n2 is defined as the lowest node in T that has both n1 and n2 as descendants (where we allow a node to be a descendant of itself).




The LCA of n1 and n2 in T is the shared ancestor of n1 and n2 that is located farthest from the root.




For example in the above graph,

LCA of 10 and 14 is 12

LCA of 14 and 8 is 8

LCA of 10 and 22 is 20




If any key is invalid or not present, print “none” in file.




<ol start="9">

 <li><strong>Find Floor and Ceil of a key in BST : </strong>​Floor(int key)​ ​Floor of key means, given a key you need to find the node equal or the largest key smaller than given key. For example, in the above example,</li>

</ol>

Floor(21) prints “20”

Floor(4) prints “4”

Floor(3) prints “none”




<strong> </strong>​ceil(int key)​ ​Ceil of key means, given a key you need to find the node equal or the smallest key larger than given key. For example, in the above example,

Ceil(21) prints “22”

Ceil(4) prints “4”

Ceil(22) prints “none”

5

<ol start="10">

 <li><strong>Determining the distance between pairs of nodes in a tree</strong>​: ​dist(int key1, int key2)</li>

</ol>




Given two keys of BST, the distance between two nodes is the minimum number of edges to be traversed to reach one node from other. For example in the above example,

dist(8, 22) is 2 dist(10,22) is 4

If any key is not valid, print “none” in file.

<strong> </strong>

<strong> </strong>

<strong> </strong>

<strong><u>Red Black Tree Insertion (15pts):</u> </strong>

<strong> </strong>

In this part, modify your code to handle Red Black Tree insertion portion only. There will be no deletion, therefore your tree will remain balanced. The insert method used may be slightly different for the C++ and the Java sections. Please follow the instructions accordingly.

<strong> </strong>

<strong><u>C++ Section:</u> </strong>

<ol start="11">

 <li><strong>Insert to maintain balance in tree </strong>​: ​insertRB(int key): ​Follow the insertion procedure described in ​ ​<strong>Data Structures and Algorithms in C++, 2nd </strong></li>

</ol>

<strong>Edition, M. T. Goodrich, R. Tamassia, D. M. Mount, February </strong>

<strong>2011</strong>​[<u>​</u><a href="https://doc.lagout.org/programmation/Java/Data%20Structures%20and%20Algorithms%20in%20Java%20%286th%20ed.%29%20%5BGoodrich%2C%20Tamassia%20%26%20Goldwasser%202014-01-28%5D.pdf">link</a>​]




Sample example from book,




<table width="705">

 <tbody>

  <tr>

   <td width="157">insertRB 4 insertRB 7 insertRB 12 insertRB 15 insertRB 3 insertRB 5 insertRB 14 insertRB 18 insertRB 16 insertRB 17</td>

   <td width="548"> </td>

  </tr>

  <tr>

   <td colspan="2" width="705"> </td>

  </tr>

 </tbody>

</table>

<strong><u>Java Section:</u> </strong>

<ol start="12">

 <li><strong>Insert to maintain balance in tree </strong>​: ​insertRB(int key): ​Follow the insertion procedure described in section 3.3 of <u>​Algorithms, 4th Edition</u>​ by Robert Sedgewick and</li>

</ol>

Kevin Wayne

Sample example from book,







<strong><u>Both Sections:</u> </strong>

<ol start="13">

 <li><strong>Black Height of a Red-Black Tree : </strong>​Black height is number of black nodes on a path from a node to a leaf (excluding given node). Leaf nodes are also counted black nodes.</li>

</ol>

getBlackHeight(int key)

In the above scenario, ​getBlackHeight(14)​would print “2” to file. Print “none” if it’s an invalid key.




<strong><u>Sample Input/output format:</u> </strong>

<ul>

 <li>The first integer 1 or 2 indicates this is the input file for part 1 or 2.</li>

 <li>The second integer n implies that there are n lines below.</li>

 <li>You can assume all numbers will be of Integer datatype.</li>

 <li>The command and corresponding input/output can be understandable from the sample test cases given bellow.</li>

 <li>For part2, each line of output should end with r
 and there will be an additional line at the end. Match your output exactly with provided test cases.</li>

</ul>

<strong><u>Test Cases:</u> </strong>

Test cases will be given for each of the 12 functionalities listed above. Your score will be based on how many complete units you are passing. For example, if you only complete basic operations, you will get 10pts. If you do basic and traversals you would get total of 25 pts.

<strong> </strong>

<table width="624">

 <tbody>

  <tr>

   <td width="312"><strong>Sample Input </strong></td>

   <td width="312"><strong>Sample Output </strong></td>

  </tr>

  <tr>

   <td width="312">2 17 insert 20 insert 22 insert 8 insert 12 insert 4 insert 10 insert 14 height 10 height 22 height 20 height 12 delete 10 delete 15 search 14 search 15 range 1 22 range 11 17 </td>

   <td width="312">310 2 deleted deletion failed found not found8026 </td>

  </tr>

  <tr>

   <td width="312">2 9 postorder levelorder insert 20 insert 22 insert 8 insert 12 insert 4 postorder levelorder </td>

   <td width="312">none none4 12 8 22 2020 8 22 4 12  </td>

  </tr>

  <tr>

   <td width="312">2 19 insert 20 insert 22 insert 8 insert 12 insert 4 insert 10 insert 14 lca 4 10 lca 20 14 lca 11 20 ceil 21 ceil 22 ceil 23 floor 5 floor 4 floor 3 dist 10 22 dist 4 14 dist 1 0</td>

   <td width="312">8 20 none 22 22 none 4 4 none 4 3 none  </td>

  </tr>

 </tbody>

</table>

<strong> </strong>

<strong> </strong>

<table width="624">

 <tbody>

  <tr>

   <td width="117"><strong>Section </strong></td>

   <td width="299"><strong>RB Tree Sample Input  </strong></td>

   <td width="208"><strong>RB Tree Sample Output </strong></td>

  </tr>

  <tr>

   <td width="117">C++</td>

   <td width="299">2 13 insertRB 4 insertRB 7 insertRB 12 insertRB 15</td>

   <td width="208">2214 7 16 4 12 15 18 35 17  </td>

  </tr>

  <tr>

   <td width="117"> </td>

   <td width="299">insertRB 3 insertRB 5 insertRB 14 insertRB 18 insertRB 16 insertRB 17 Bheight 14 Bheight 16 levelorder</td>

   <td width="208"> </td>

  </tr>

  <tr>

   <td width="117">Java</td>

   <td width="299">2 13 insertRB 1 insertRB 2 insertRB 3 insertRB 4 insertRB 5 insertRB 6 insertRB 7 insertRB 8 insertRB 9 insertRB 10 Bheight 1 Bheight 4 levelorder  </td>

   <td width="208">134 2 8 1 3 6 10 5 7 9 </td>

  </tr>

 </tbody>

</table>

<strong> </strong>

<strong> </strong>

<h2>Part 3: Programming Environment and Grading</h2>

<strong> </strong>

Assignments will be tested in a Linux environment. You will be able to work on the assignments using the Linux workstations in HAAS and LAWSON (use your username and password).




<strong>3A: Java </strong>

<ul>

 <li>Compiler we use: javac (v10.0.2)</li>

 <li>File to submit: ​Rhymer​.java, BinarySearchTree.java, Node.java, Main.java</li>

</ul>




Your project must compile using the javac compiler (v10.0.2) on data.cs.purdue.edu. Main.java is provided to you so that you can generate output file on your own to see if your code works correctly, you may change it as your wish.




<strong>Compiling process</strong>​: ​<strong>following commands assume you are at project root and you have NOT changed project file structure! </strong>●    To compile Main:

javac src/*

<ul>

 <li>To run Main: java -cp src/ Main InputFilePath OutputFilePath</li>

</ul>

Note: You should replace InputFilePath OutputFilePath with actual file path in the above command.




<strong>Grading process: </strong>

<ol>

 <li>Compiling your program with JUnit test files using javac v10.0.2.</li>

 <li>Running JUnit tests. It read input files and manipulates data structures implemented by you and see if it works as expected. Any forms of difference between your output and expected output will cause points deduction.</li>

 <li>Inspecting your source code.</li>

</ol>




<strong>3B: C++ </strong>

The compilation will be done using g++ and makefiles. You <u>​must submit</u>​ all the source code as well as the Makefile that compiles your provided source code into an executable named “program”.




Your project must compile using the standard g++ compiler (v 4.9.2) on data.cs.purdue.edu.  For convenience, you are provided with a template Makefile and C++ source file. You are allowed to modify such file at your convenience as long as it follows the I/O specification. Note some latest features from C++14 are not available in g++ 4.9.




The grading process consists of:




<ol>

 <li>Compiling and building your program using your supplied makefile.</li>

 <li>The name of the produced executable program must be “program” (must be lowercase)</li>

 <li>Running your program automatically with several test input files we have pre-made according to the strict input file format of the project and verifying correct output files thus follow the above instruction for output precisely – do not “embellish” the output with additional characters or formatting – if your program produces different output such as extra prompt and space, points will be deducted.</li>

 <li>Inspecting your source code.</li>

</ol>




The input to the programming projects will be via the command line:

<strong>program input-test1.txt output-test1.txt </strong>




The file output-test1.txt will be tested for proper output.


