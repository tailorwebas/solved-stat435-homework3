Download Link: https://assignmentchef.com/product/solved-stat435-homework3
<br>
The homework comes with a test data set ”test-data.R” in ”dump” format. For the test data, <em>n </em>= 100, and <em>x</em><sub>1</sub><em>,…,x<sub>n </sub></em>are equi-spaced in [0<em>,</em>2<em>π</em>]. The true conditional expectation is <em>f</em>(<em>x</em>) = sin(<em>x</em>), and the error sd is <em>σ </em>= 0<em>.</em>4.

<h1>1.     Experiments with Turbo</h1>

Turbo is an expansion based smoother that fits 2nd order (linear) splines. It is described in the article <em>Flexible Parsimonious Smoothing and Additive Modeling </em>by J.H. Friedman and B.W. Silverman (Technometrics, Vol. 31, No. 1, 1989, pp 3 – 39.

<ol>

 <li>Define basis functions <em>B<sub>i</sub></em>(<em>x</em>) = (<em>x</em>−<em>x<sub>i</sub></em>)<sub>+</sub><em>,i </em>= 1<em>,…,n</em>−1, and</li>

</ol>

<em>B<sub>n</sub></em>(<em>x</em>) = 1. Write a function truncated.power.design.matrix(x) that generates the <em>n </em>× <em>n </em>design matrix for this set of basis functions.

<ol>

 <li>Install the package ”leaps” and take a look at the documentation. Write a function</li>

</ol>

regsubsets.fitted.values &lt;- function(X, regsubsets.out, nterm) that computes the fitted values for a model with nterm terms.

<ol>

 <li> For the test data produce a plot of residual sum of squares as a function of the number <em>k </em>of basis functions in the model.</li>

 <li> Plot the GCV score as a function of <em>k</em>. Surprised? Why? Explanation?</li>

 <li>F&amp;S (pp 9–10) propose to fix this problem by charging 3 degrees of freedom for each of <em>B</em><sub>1</sub><em>,…,B<sub>n</sub></em><sub>−1 </sub>entered into the model. Plot this modified GCV score as a function of the number of basis functions in the model. Surprised? Problems with the F&amp;S definition of GCV? (If you have trouble figuring out where the constant term is included in the model, you may charge 3 degrees of freedom for each of <em>B</em><sub>1</sub><em>,…B<sub>n</sub></em>.)</li>

 <li> Restricting yourself to suitable small values of <em>k</em>, find the ”forward” and ”backward” models with the smallest (modified) GCV scores and plot them.</li>

</ol>

1

<h1>2.     Experiments with order 2 smoothing splines</h1>

Training data and basis functions as in (1) above. Define the <em>n </em>× <em>n </em>matrix <em>X </em>by <em>X<sub>ij </sub></em>= <em>B<sub>j</sub></em>(<em>x<sub>i</sub></em>).

An order 2 smoothing spline is a function of the form

<table width="318">

 <tbody>

  <tr>

   <td width="42"><em>g</em>(<em>x</em>)</td>

   <td width="25">=</td>

   <td width="251">X<em>a</em>ˆ<em><sub>j</sub>B<sub>j</sub></em>(<em>x</em>)<em>,</em>where</td>

  </tr>

  <tr>

   <td width="42"><strong>a</strong>ˆ</td>

   <td width="25">=</td>

   <td width="251">argmin<strong><sub>a </sub></strong>k<strong>y </strong>− <em>X</em><strong>a</strong>k<sup>2 </sup>+ <em>λ</em><strong>a</strong><em><sup>T</sup></em>Ω<strong>a</strong><sup>i </sup>with h</td>

  </tr>

  <tr>

   <td width="42">Ω</td>

   <td width="25">=</td>

   <td width="251">diag(0<em>,</em>1<em>,…,</em>1<em>,</em>0)<em>.</em></td>

  </tr>

 </tbody>

</table>

The vector of predicted values for the training sample is <strong>y</strong>ˆ = <em>X</em><strong>a</strong>ˆ.

<ul>

 <li> Show that</li>

</ul>

<strong>y</strong>ˆ  = <em>X</em>(<em>X<sup>T</sup>X </em>+ <em>λ</em>Ω)<sup>−1</sup><em>X<sup>T</sup></em><strong>y </strong>=    <em>S<sub>λ </sub></em><strong>y</strong><em>.</em>

<ul>

 <li>Read the data in the file test-data.R. Use the glmnet package to plot data and spline for <em>λ </em>= 0<em>,</em>1<em>,</em>10<em>,</em>10<sup>6</sup>. Verify (graphically) that the spline for <em>λ </em>= 10<sup>6 </sup>is very close to the least squares line.</li>

 <li> Use the glmnet package to find the optimal value of <em>λ </em>by cross-vaildation. Print out <em>λ<sub>opt </sub></em>and plot the corresponding spline.</li>

</ul>

<ol start="3">

 <li><strong>ISLR Section 6.8 Problem 1 </strong></li>

 <li><strong>ISLR Section 6.8 Problem 4 </strong></li>

</ol>