# Introduction to R



## The **RStudio** Interface 

We will begin by looking at the RStudio software interface. Refer to Figure 1 as you follow the instructions below.

Launch RStudio. You will see a window that looks like Fig. 1. There are four panels of the window:

  - The R Command Console is where you type R commands for immediate execution.

  - The Notebook in the upper left portion of the window is an area for editing R source code for scripts and functions and for viewing R data frame objects. New tabs will be added as new R code files and data objects are opened.

  - The Notebook in the upper right portion of the window is an area for browsing the variables in the R workspace environment and the R command line history.
    
   - The Notebook in the lower right portion of the window has several tabs. The Files tab is an area for browsing the files in the current working directory. The Plot tab is for viewing graphics produced using R commands. The Packages tab lists the R packages available. Other packages can be loaded. The Help tab provides access to the R documentation. The Viewer tab is for viewing local web content in the temporary session directory (not files on the web).
    
### Bottom Left Pane {-}

Let’s begin with the Console. This is where you type `R` commands for immediate execution. Click in the Command Console,  ">" symbol is the system prompt. You should see a blinking cursor that tells you the console is the current focus of keyboard input. Type:

```r
1+2
```

```
## [1] 3
```

The result tells you that the line begins with the first (and only) element of the result which is the number 3. You can also execute R’s built-in functions (or functions you add).  Type the following command. 

```r
exp(pi)
```

```
## [1] 23.14069
```
    
    
In `R`, "pi" is a special constant to represent the number  and "exp" is the exponential function. The result tells you that the first (and only) element of the result is the number $e^{\pi}=$ 23.14069.

### Bottom Right Pane {-}

Now let’s look at the *Files* tab of the notebook at the lower right of the window. Every `R` session has a working directory where `R` looks for and saves files. It is a good practice to create a different directory for every project and make that directory the working directory. For example, let’s make a new directory called *MyDirectory*. (You can chose another name if you wish). 

1) Click on the **Files** tab of the notebook. You should see a listing of files in your default working directory.

2) Click on the small button with an ellipsis image on the right side of the file path above the directory listing.

3) Navigate to the folder where you want to create the new directory and click the **OK** button.

4) Click on the **New Folder** button just below the Files tab (see right).

5) Type **MyDirectory** in the panel that opens click on the folder in the Notebook.

6) Click the **More** button to the right of the New Folder button and select the menu option **Set as Working Directory**. This new folder is now the working directory for the current R session. This menu option is a short cut for a command that was automatically entered into the R console.

### Top Right Pane {-}
 Next we will look at the *R environment*, also called the *R workspace*. This is where you can see the names and other information on the variables that were created during your `R` session and are available for use in other commands.

In the `R` console type: 


```r
a = 29.325
b = log(a)
c = a/b
```

Look at the Environment pane. The variables `a`, `b`, and `c` are now part of your R work space. You can reuse those variables as part of other commands.

In the `R` console type: 

```r
v= c(a, b, c)
v
```

```
## [1] 29.325000  3.378440  8.680041
```

The variable `v` is a vector created using the *concatenate* function `c()`. (The concatenate should not be confused with the variable c that was created earlier. Functions are always followed by parentheses that contain the function arguments.) This function combines its arguments into a vector or list. Look at the Environment panel. The text `num [1:3]` tells us that the variable `v` is a vector with elements `v[1]`, `v[2]`, and `v[3]`.

### Top Left Pane {-}

Now let’s look at the `R` viewer notebook. This panel can be used to data which are data frame objects or *matrix objects* in `R`.

We will begin by taking advantage of a data frame object that was built into `R` for demonstration purposes. We will copy it into a data frame object. In the `R` console, type:


```r
df = mtcars
```

Let's view the data. On the right side of the entry for the `df` object is a button we can use to view the entries of the data frame (see green arrow below). Click on the View Button. 

If your look in the notebook area in the upper left portion of the window, you can see a spreadsheet-like view of the data. This is for viewing only; you cannot edit the data. Use the scroll bars to view the data entries.

You can also list the data in the console by typing the name of the data fame object:


```r
df
```

```
##                      mpg cyl  disp  hp drat    wt  qsec vs am gear carb
## Mazda RX4           21.0   6 160.0 110 3.90 2.620 16.46  0  1    4    4
## Mazda RX4 Wag       21.0   6 160.0 110 3.90 2.875 17.02  0  1    4    4
## Datsun 710          22.8   4 108.0  93 3.85 2.320 18.61  1  1    4    1
## Hornet 4 Drive      21.4   6 258.0 110 3.08 3.215 19.44  1  0    3    1
## Hornet Sportabout   18.7   8 360.0 175 3.15 3.440 17.02  0  0    3    2
## Valiant             18.1   6 225.0 105 2.76 3.460 20.22  1  0    3    1
## Duster 360          14.3   8 360.0 245 3.21 3.570 15.84  0  0    3    4
## Merc 240D           24.4   4 146.7  62 3.69 3.190 20.00  1  0    4    2
## Merc 230            22.8   4 140.8  95 3.92 3.150 22.90  1  0    4    2
## Merc 280            19.2   6 167.6 123 3.92 3.440 18.30  1  0    4    4
## Merc 280C           17.8   6 167.6 123 3.92 3.440 18.90  1  0    4    4
## Merc 450SE          16.4   8 275.8 180 3.07 4.070 17.40  0  0    3    3
## Merc 450SL          17.3   8 275.8 180 3.07 3.730 17.60  0  0    3    3
## Merc 450SLC         15.2   8 275.8 180 3.07 3.780 18.00  0  0    3    3
## Cadillac Fleetwood  10.4   8 472.0 205 2.93 5.250 17.98  0  0    3    4
## Lincoln Continental 10.4   8 460.0 215 3.00 5.424 17.82  0  0    3    4
## Chrysler Imperial   14.7   8 440.0 230 3.23 5.345 17.42  0  0    3    4
## Fiat 128            32.4   4  78.7  66 4.08 2.200 19.47  1  1    4    1
## Honda Civic         30.4   4  75.7  52 4.93 1.615 18.52  1  1    4    2
## Toyota Corolla      33.9   4  71.1  65 4.22 1.835 19.90  1  1    4    1
## Toyota Corona       21.5   4 120.1  97 3.70 2.465 20.01  1  0    3    1
## Dodge Challenger    15.5   8 318.0 150 2.76 3.520 16.87  0  0    3    2
## AMC Javelin         15.2   8 304.0 150 3.15 3.435 17.30  0  0    3    2
## Camaro Z28          13.3   8 350.0 245 3.73 3.840 15.41  0  0    3    4
## Pontiac Firebird    19.2   8 400.0 175 3.08 3.845 17.05  0  0    3    2
## Fiat X1-9           27.3   4  79.0  66 4.08 1.935 18.90  1  1    4    1
## Porsche 914-2       26.0   4 120.3  91 4.43 2.140 16.70  0  1    5    2
## Lotus Europa        30.4   4  95.1 113 3.77 1.513 16.90  1  1    5    2
## Ford Pantera L      15.8   8 351.0 264 4.22 3.170 14.50  0  1    5    4
## Ferrari Dino        19.7   6 145.0 175 3.62 2.770 15.50  0  1    5    6
## Maserati Bora       15.0   8 301.0 335 3.54 3.570 14.60  0  1    5    8
## Volvo 142E          21.4   4 121.0 109 4.11 2.780 18.60  1  1    4    2
```

The columns are labeled with the names of the variables and the rows are labeled with the names of each car. Each row represents the data values for one car; that is, each row is one observation.

## R Data Types 

At its core, `R` is an objected-oriented computational and programming environment. Everything in `R` is an object belonging to a certain *class*.
`R `can represent different types of data. The types include `numeric`, `integer`, `complex`, `logical`, and `character`. We will look at some examples.

### Numbers {-}

There are different types of numeric objects.  Specifically, we will first consider real numbers (can have decimal values) and integers. We can examine how `R` stores these types of numbers using the `class()` function. 

We will begin with decimal numbers.


```r
a = 17.45
a
```

```
## [1] 17.45
```

```r
class(a)
```

```
## [1] "numeric"
```

```r
b = 5
b 
```

```
## [1] 5
```

```r
class(b)
```

```
## [1] "numeric"
```

Both the variables `a` and `b` are `numeric` objects. When you type a number `R` will default to treating it as a `numeric` object which allows decimals. 
You can use the `as.integer()` function to create a variable that is specifically an integer number. 


```r
a = as.integer(a)
a
```

```
## [1] 17
```

```r
class(a)
```

```
## [1] "integer"
```

```r
b = as.integer(b)
b 
```

```
## [1] 5
```

```r
class(b)
```

```
## [1] "integer"
```

### Logical {-}

Logical values are either "true" or "false" and are created by logical statements that compare variables. There are several ways to do logical statements.  To check if two values or objects are equal to each other we use "==".  To see if a value/object is greater than or less than another we use the "<", ">", "<=", or ">=". 


```r
b = 5
2+3 == b
```

```
## [1] TRUE
```

```r
n = (10<11)
n
```

```
## [1] TRUE
```

```r
class(n)
```

```
## [1] "logical"
```

```r
e = (b >10)
class(e)
```

```
## [1] "logical"
```

The symbols "&" "|", and "!" are used for the logical operations "and", "or", and "not". Two logical expressions connected by & (and) are true only if both are true. Two logical expressions connected by | (or) are true if either are true.  The ! (not) operation turns a true into a false and vice-versa.


```r
e & n
```

```
## [1] FALSE
```

```r
e | n 
```

```
## [1] TRUE
```

```r
!n
```

```
## [1] FALSE
```

### Character {-}

`Character` values are text. They are often used as data values and labels. 


```r
first = "George"
first 
```

```
## [1] "George"
```

```r
class(first)
```

```
## [1] "character"
```

```r
last = "Washington"
last
```

```
## [1] "Washington"
```

```r
class(last)
```

```
## [1] "character"
```
There are several functions that can operate on character strings.


```r
full = paste(first, last)
full 
```

```
## [1] "George Washington"
```

```r
nchar(full)
```

```
## [1] 17
```

```r
tolower(full)
```

```
## [1] "george washington"
```

```r
toupper(full)
```

```
## [1] "GEORGE WASHINGTON"
```

The function `paste()` concatenates two or more character strings with a separator, which is a space by default. The function `nchar()` returns the number of characters in a string. The functions `tolower()` and `toupper()` changes any upper case characters to lower case and vice-versa.

### Vectors {-}

All the objects we have created this far are single element **vectors**.  `R` is a vectorized language, meaning most of the procedures, functions, and operations have been optimized to work with vectors. It is often advantageous to utilize this feature.  A vector is a one dimensional array of the same data type.  We can use the concatenate function, `c()`, to create vectors, and to make a vector larger. 


```r
v1 = c(19, 390.3, pi, -32.1)
v1
```

```
## [1]  19.000000 390.300000   3.141593 -32.100000
```

```r
class(v1)
```

```
## [1] "numeric"
```

```r
v2 = c(1.1, 6, -9.4, 32.1)
v2
```

```
## [1]  1.1  6.0 -9.4 32.1
```

```r
class(v2)
```

```
## [1] "numeric"
```

```r
v3 = c(v1, first)
class(v3)
```

```
## [1] "character"
```

```r
v4 = c(first, last)
class(v4)
```

```
## [1] "character"
```


The **length()** function can be used to obtain the number of elements in a vector. 


```r
length(v1)
```

```
## [1] 4
```

Vectors can be used in arithmetic computations. If the two vectors are of the same length, the computations are performed element-by-element.


```r
v1 + v2
```

```
## [1]  20.100000 396.300000  -6.258407   0.000000
```

```r
v1 * v2
```

```
## [1]    20.90000  2341.80000   -29.53097 -1030.41000
```

Single numbers (scalars) will operate on all the vector elements in an expression. 


```r
5*v1
```

```
## [1]   95.00000 1951.50000   15.70796 -160.50000
```

```r
v1/3
```

```
## [1]   6.333333 130.100000   1.047198 -10.700000
```

Individual elements of a vector can be obtained using an index in square brackets. A negative index removes that element from the vector. The `v2[-1]` is the vector `v2` with the first element removed. The concatenate function can be used to obtain two or more elements of a vector in any desired order. Here `v1[c(3,2)]` returns the third and second elements of the vector `v1`.


```r
v1[3]
```

```
## [1] 3.141593
```

```r
v2[-1]
```

```
## [1]  6.0 -9.4 32.1
```

```r
v3[c(3,2)]
```

```
## [1] "3.14159265358979" "390.3"
```

### Matrices {-}
