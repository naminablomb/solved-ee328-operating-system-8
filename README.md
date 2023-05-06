Download Link: https://assignmentchef.com/product/solved-ee328-operating-system-8
<br>
<h1>1 PROBLEM</h1>

<h2>1.1 DESCRIPTION</h2>

Writeaprogramthatcalculatesthematrixmultiplicationwithallthesituationconsidering. You canseethedetailintheendofchapter4of<em>OPERATINGSYSTEMCONCEPTSWITHJAVA(Seventh Edition)</em>, page 162.

<h1>2 ALGORITHM</h1>

<table width="567">

 <tbody>

  <tr>

   <td width="154">be described as follows:</td>

   <td width="104"></td>

   <td width="36"></td>

   <td width="29"></td>

   <td width="103"></td>

   <td width="64"></td>

   <td width="60"></td>

   <td width="16"></td>

  </tr>

  <tr>

   <td width="154"> <em>a</em>11 <em>a</em>12 <em>··· </em> <em>a</em>21 <em>a</em>22 <em>···</em> …             …              … <em>a</em><em>m</em>1 <em>a</em><em>m</em><a href="#_ftn1" name="_ftnref1"><sup>[1]</sup></a> <em>···</em>where</td>

   <td width="104"><em>a</em>1<em>n </em>  <em>b</em>11<em>a</em>2<em>n </em><sup>  </sup><em>b</em>21 ..<sub>. </sub><em>×</em> ..<sub>.</sub>  <em>a</em><em>mn                 b</em><em>n</em>1</td>

   <td width="36"><em>b</em>12 <em>b</em>22…<em>b</em><em>n</em>2</td>

   <td width="29"><em>··· ···</em>…<em>···</em></td>

   <td width="103"><em>b</em>1<em>q </em>  <em>c</em>11<em>b</em>2<em>q </em><sup>  </sup><em>c</em>21 ..<sub>. </sub><em>=</em> ..<sub>.</sub>  <em>b</em><em>nq     c</em><em>m</em>1</td>

   <td width="64"><em>c</em>12            <em>··· c</em>22            <em>···</em><sup>.</sup>..           <sup>.</sup>.. <em>c</em><em>m</em>2 <em>···</em></td>

   <td width="60"><em>c</em>1<em>q </em><em>c</em>2<em>q </em><sup> </sup>… <em>c</em><em>mq</em></td>

   <td width="16">(1)</td>

  </tr>

  <tr>

   <td width="154"><em>n</em></td>

   <td width="104"></td>

   <td width="36"></td>

   <td width="29"></td>

   <td width="103"></td>

   <td width="64"></td>

   <td width="60"></td>

   <td rowspan="2" width="16">(2)</td>

  </tr>

  <tr>

   <td colspan="7" width="550"><em>c<sub>i j </sub>= </em><sup>X </sup><em>a<sub>ir</sub>b<sub>r j </sub>= a<sub>i</sub></em><sub>1</sub><em>b</em><sub>1<em>j </em></sub><em>+a<sub>i</sub></em><sub>2</sub><em>b</em><sub>2<em>j </em></sub><em>+···+a</em><sub>1<em>n</em></sub><em>b<sub>nj</sub></em>,<em>i = </em>1,2,<em>··· </em>,<em>m</em>; <em>j = </em>1,2,<em>··· </em>,<em>q</em><em>r=</em>12.2 MULTI-THREAD PROGRAMMING</td>

  </tr>

 </tbody>

</table>

1

Figure 3.1: Screenshot of Matrix Multiplication

<h2>2.3 ROBUSTNESS CONSIDERATION</h2>

The user input process requires great efforts to avoid illegal input and make sure the program execute normally. First we require user to input 4 integers to denote the rows and columns and create 2 zero matrices. The column number of [<em>A</em>] needs to be the same as the row number of [<em>B</em>] and thus a detection is needed. In the meantime we require the user to input a row at a time so if any illegal input exists the user is supposed to input this row again until he finishes input.

<h1>3 RESULTS</h1>

<h2>3.1 ENVIRONMENT</h2>

<ul>

 <li>Windows 10</li>

 <li>Java Development Kit 1.8.0_131</li>

 <li>Eclipse</li>

</ul>

3.2 SCREENSHOTS OF THE RESULT

We use command line to compile and execute the program. The result is shown in Fig. 3.1.

<h2>3.3 THOUGHTS</h2>

It is the first time that I learn multi-thread programming. Although the algorithm is easy it still consumed me lots of time to master multi-thread programming, which benefits me a great deal.

2

<a href="#_ftnref1" name="_ftn1">[1]</a> .1 MATRIX MULTIPLICATION

Matrix multiplication is able to be executed when the matrices are like [<em>A</em>]<em><sub>m</sub></em><em>×n×</em>[<em>B</em>]<em><sub>n</sub></em><em>×q </em>and can

We create <em>m×q </em>threads to calculate each element in the result matrix [<em>C</em>]<em><sub>m</sub></em><em>×q </em>using the formula above. After all sub-threads have been terminated, the main thread will print the result. Class <em>CalMatrix </em>is supposed to extend class <em>Thread </em>and override the method <em>run()</em>. Method <em>join() </em>is necessary in the main thread as well.