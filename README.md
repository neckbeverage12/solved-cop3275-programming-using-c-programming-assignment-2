Download Link: https://assignmentchef.com/product/solved-cop3275-programming-using-c-programming-assignment-2
<br>
<ol>

 <li>You have to upload your codes in both Canvas and the Judge system at <a href="https://cop3275.cise.ufl.edu/">https: </a><a href="https://cop3275.cise.ufl.edu/">//cop3275.cise.ufl.edu</a></li>

 <li>For guide on how to access the Judge, visit Judge Access Page under Pages section in Canvas.</li>

 <li>The judge will run test cases against your code and assign it a grade. You can have multiple submission for the same problem but you have to choose which one is the final (we will consider your final submission for grading). Canvas is only used for record keeping.</li>

 <li>When uploading on Canvas, zip your programs in a zipfile with your ufid as name (nothing more, just 8 digit ufid, for instance 12345678.zip). Add a .txt extension to all your files. i.e. name your files (inside the zipped archive) p1.c.txt, p2.c.txt, and so on.</li>

 <li>For all the problems input is read from standard input (e.g. read using scanf) and must be written to standard output (e.g. printf).</li>

 <li><strong>Don’t print extra stuff. Since the assignments are automatically graded, if the output doesn’t match the expected output, you will not get the points. </strong>For instance: If the problem is to read a number and return its square, the expected output is a number (i.e. printf(“%d”,i*i). If you print using something like printf(“square is %d”,i*i); you will not receive any points.</li>

 <li>The assignment is due on 11:59 pm Monday Oct. 14, 2019. There is a 20% penalty for late submission of one day. No submission is accepted beyond that time.</li>

</ol>

<h1>Problem 1: DNA!       [20 Points]</h1>

Expected LoC: 30

DNA sequence is a succession of letters that indicate the order of nucleotide bases. Each strand comes with a complement of it to form the double helix structure that we know as the DNA! The bases are represented using A, T, C, and G. The complement strand has the complementing bases in each and all the positions. Bases that complement each other are A &#x2194; T and C &#x2194; G. In this problem you are tasked with implementing a program that given two strands of nucleotide bases as input, counts and prints the number of incompatibilities between them (the complement of a strand would have 0 differences). In other words, we expect A and T, or C and G to appear together in a line. For instance if A appears with anything other than T in the same line, it counts as one incompatibility. The input contains the number of nucleotide bases N in the first line. The following N lines each would contain two characters that are space separated. The first character denotes the base in the original strand and the second character denotes the base in the second strand.

<ul>

 <li>Hint: you can use scanf with %c to scan one character from input at a time. If scanf sees a whitespace in its first argument, it skips over all whitespace characters until it reaches a non-whitespace character. i.e., scanf(” %c %c”, &amp;c1,&amp;c2).</li>

</ul>

Examples:

<table width="530">

 <tbody>

  <tr>

   <td width="175">Input</td>

   <td width="175">Expected output</td>

   <td width="180">Explanation</td>

  </tr>

  <tr>

   <td width="175">8A TC GG CG GC TT TT AT C</td>

   <td width="175">4</td>

   <td width="180">(G,G) (C,T) (T,T) (T,C) are the pairs that are not complement of each other.</td>

  </tr>

 </tbody>

</table>

<h1>Problem 2: Stock Market!           [40 points]</h1>

Expected LoC: <em>&lt; </em>60

In this problem you are given the values of market index through time. You are tasked to compute:

<ul>

 <li>The day with maximum value.</li>

 <li>The day with minimum value.</li>

 <li>Average value overall.</li>

 <li>Number of days with higher (strictly) than average value.</li>

</ul>

Input format:

First comes N the number of days for which we are getting values, in a line.

Each of the following lines would have the value for one day, starting with day 1.

Output format:

In the first line of output, print the day with maximum value and its corresponding maximum value separated with a space. Print to exactly 2 decimal places.

In the second line, same as above but for minimum.

In third line print the average value to 2 decimal places.

In fourth line print the number of days with a value strictly greater than the average.

Example:

<table width="530">

 <tbody>

  <tr>

   <td width="148">Input</td>

   <td width="148">Expected output</td>

   <td width="233">Explanation</td>

  </tr>

  <tr>

   <td width="148">511823.5311800.9211788.7711792.9811805.04</td>

   <td width="148">1 11823.533 11788.7711802.252</td>

   <td width="233">The highest value is 11823.53 which occurs on day 1. The lowest value is 11788.77 which occurs on day 3. Average (sum divided by count) is 11802.25 There are 2 days with a number greater than 11802.25 namely day 1 with value 11823.53 and day 5 with value 11805.04</td>

  </tr>

 </tbody>

</table>

<ul>

 <li>If you get multiple days with the same highest/lowest value, print the first one. You can do so by only updating your temporary max (min ) only if the current value is strictly bigger (smaller).</li>

 <li>Store the input as you read them into an array. Since arrays are indexed from 0 to n-1, corresponding day to ith element is i+1.</li>

 <li>Write a function for each task (e.g. a function that finds the maximum element and returns its index in the input array, then you can easily find the value using that index).</li>

</ul>

<h1>Problem 3: Mind Reader!                  [40 points]</h1>

Expected LoC: 30

In this problem you are asked to write a program that finds the number the user has in mind. It works by guessing a number and asking the user whether it is greater than or less than the number they have in mind until it guesses the number. A negative input by user means the number they have in mind is less than the number the computer prints. A positive number means the number they have in mind is greater than the number computer guesses. Zero means the computer got the number right and program exits.

The expected method of finding the number is through binary search. It works by guessing the value right in the middle of the range of possible values and based on user input shrinking the range of possible values.

For example, at first when the range of values is [0,1000] the number 500 is the guess. If the user input is negative, it means that the value in mind is less than 500, effectively discarding all the number greater than or equal to it. In other words, the possible range of values is now shrunk to [0, 499]. Now the value in the middle is 249 and that is what the computer guesses. Now the user inputs a positive number which means the number they have in mind is bigger than 249 which means all the numbers below that can be easily excluded. In other words, the possible range is now [250, 499]. We continue this until the user’s number is found.

The minimum and maximum values for the range are given in the first line of input as two integers (space separated). Then the following lines are the user’s input (i.e., your code is supposed to guess Judge’s number) that are either 1, -1 or 0 with 0 indicating the number has been found and your program can now exit.

Whenever the range of values contains an even number of elements, consider the element to the left of the middle as the guess. For instance, in range [2,5] the middle number is 3.

<ul>

 <li>This is an application of binary search algorithm. Make sure you understand the algorithm first.</li>

 <li>Run some small examples for yourself with pen and paper.</li>

 <li>Storing the valid range’s end points as variables and modifying them based on input is the suggested way!</li>

 <li>Note that the end points might be negative (e.g., [-10,-5] or [-10,12]).</li>

</ul>

Example (next page):




<table width="493">

 <tbody>

  <tr>

   <td width="64">Input</td>

   <td width="122">Expected output</td>

   <td width="307">Explanation</td>

  </tr>

  <tr>

   <td width="64">0 511-1-11111-1-10</td>

   <td width="122">2551276395111119123121120</td>

   <td width="307">* assume the user’s number is 120Computer prints: 255User input: -1 (range is now 0 to 254) Computer prints: 127User input: -1 (range is now 0 to 126) Computer prints: 63User input: 1 (range is now 64 to 126) Computer prints: 95User input: 1 (range is now 96 to 126)Computer prints: 111User input: 1 (range is now 112 to 126) Computer prints: 119User input: 1 (range is now 120 to 126)Computer prints: 123User input: -1 (range is now 120 to 122) Computer prints: 121User input: -1 (range is now 120 to 120)Computer prints: 120User input: 0</td>

  </tr>

 </tbody>

</table>


