# Tic Tac Toe - Part 3

If you made it here, then your game lets a player pick a spot on the board:

![](https://img-c.udemycdn.com/redactor/raw/article_lecture/2025-01-04_01-22-48-2a4d1739930f5cb75d49d481fa3e3980.gif)

It also doesn't let them pick a spot that's already taken.

![](https://img-c.udemycdn.com/redactor/raw/article_lecture/2025-01-04_01-22-48-be231d81b0447d3e8b6afc7b06ed6a5b.gif)

Onto the most exciting part! You will write code that determines the winner.

The `checkWin()` function
-------------------------

This function has to check for a win in every row:

![](https://img-c.udemycdn.com/redactor/raw/article_lecture/2025-01-04_01-22-48-9a602fb71f0998494f7a1c39595c99a4.gif)

every column:

![](https://img-c.udemycdn.com/redactor/raw/article_lecture/2025-01-04_01-22-48-83feaa80412bea4c8de52068643bb281.gif)

the left diagonal:

![](https://img-c.udemycdn.com/redactor/raw/article_lecture/2025-01-04_01-22-48-a6fe3ae62d52667c56e43b47f512e1f4.png)

and the right diagonal:

![](https://img-c.udemycdn.com/redactor/raw/article_lecture/2025-01-04_01-22-49-d28d854173f3179d1522abb69ef9f371.png)

## Task 6: Write the function
--------------------------

1. Create a function called checkWin.

```java
/**
 * Function name - checkWin <-------
 * @param board (char[][])
 * @return count (int)
 *
 * Inside the function:
 *   1. checkRows(): Check every row for a straight X/O  (Task 7)
 *   2. checkColumns(): Check every column for a straight X/O  (Task 8)
 *   3. checkLeft(): Check the left diagonal for a straight X/O  (Task 9).
 *   4. checkRight(): Check the right diagonal for a straight X/O  (Task 10).
 */
```

2. Parameters: The function takes one parameter: char[][] board.

```java
/**
 * Function name - checkWin
 * @param board (char[][]) <--------
 * @return count (int)
 *
 * Inside the function:
 *   1. checkRows(): Check every row for a straight X/O  (Task 7)
 *   2. checkColumns(): Check every column for a straight X/O  (Task 8)
 *   3. checkLeft(): Check the left diagonal for a straight X/O  (Task 9).
 *   4. checkRight(): Check the right diagonal for a straight X/O  (Task 10).
 */
```

**3**. Return value: The function returns a count.

```java
/**
 * Function name - checkWin
 * @param board (char[][])
 * @return count (int) <----------
 *
 * Inside the function:
 *   1. checkRows(): Check every row for a straight X/O  (Task 7)
 *   2. checkColumns(): Check every column for a straight X/O  (Task 8)
 *   3. checkLeft(): Check the left diagonal for a straight X/O  (Task 9).
 *   4. checkRight(): Check the right diagonal for a straight X/O  (Task 10).
 */
```

Tasks 7 - 10 are function calls that return an int. 
```java
/**
 * Function name - checkWin
 * @param board (char[][])
 * @return count (int)
 *
 * Inside the function:
 *   1. checkRows(): Check every row for a straight X/O  (Task 7) <————
 *   2. checkColumns(): Check every column for a straight X/O  (Task 8) <————
 *   3. checkLeft(): Check the left diagonal for a straight X/O  (Task 9). <————
 *   4. checkRight(): Check the right diagonal for a straight X/O  (Task 10). <————
 */
```
Copy their definitions inside your class.

```java
public static int checkRows(char[][] board) {
    int count = 0;
    return count;
}


public static int checkColumns(char[][] board) {
    int count = 0;
    return count;
}


public static int checkLeft(char[][] board) {
    int count = 0;
    return count;
}


public static int checkRight(char[][] board) {
    int count = 0;
    return count;
}
```

Call each function inside checkWin().

```java
public static int checkWin(char[][] board) {    
    int rows = checkRows(board); 
    
    // Math.abs returns the absolute value of a given number, removing any negative sign. 
    if (Math.abs(rows) == 3) return rows; // If the block of code consists of only one line, you can omit the curly braces.
    
    int columns = checkColumns(board);
    if (Math.abs(columns) == 3) return columns;  
    
    int leftDiagonal = checkLeft(board);
    if (Math.abs(leftDiagonal) == 3) return leftDiagonal; 
    
    int rightDiagonal = checkRight(board);
    if (Math.abs(rightDiagonal) == 3) return rightDiagonal;
    
}
```

Call `checkWin` from your for loop in main. The loop should break if the returned count is 3 or -3.
```
     if (returned count == 3) {
        // 1. print: X wins
        // 2. break the loop
      } else if (returned count == -3) {
        // 1. print: O wins
        // 2. break the loop
       }
```

## Task 7: Checking every row
--------------------------

Tasks 7 - 10 are function calls that receive and return `int`.

```java
/**
 * Function name - checkWin
 * @param board (char[][])
 * @return count (int)
 *
 * Inside the function:
 *   1. checkRows(): Check every row for a straight X/O  (Task 7) <——
 *   2. checkColumns(): Check every column for a straight X/O  (Task 8)
 *   3. checkLeft(): Check the left diagonal for a straight X/O  (Task 9).
 *   4. checkRight(): Check the right diagonal for a straight X/O  (Task 10).
 */
```

`checkRows():` will check every row for a straight X or straight O:
    - The outer loop must run through each row while the inner loop runs through every character in that row.
    - In each row, add 1 to count if there's an X. Subtract 1 if there's an O.

![](https://img-c.udemycdn.com/redactor/raw/article_lecture/2025-01-04_01-22-49-97903ae06515871fe2600946097853a9.gif)

If `count` isn't 3 or -3, reset it and move to the next row.

![](https://img-c.udemycdn.com/redactor/raw/article_lecture/2025-01-04_01-22-49-b5231bed2a1210893e4dad1323e65255.gif)

A count of 3 means X won (conversely, a count of -3 means O won).

![](https://img-c.udemycdn.com/redactor/raw/article_lecture/2025-01-04_01-22-49-8382b6d6ffe138562d2059b91b051cf8.gif)

If `count` is 3 **OR** -3, break the `checkWin` function by returning `count`.

![](https://img-c.udemycdn.com/redactor/raw/article_lecture/2025-01-04_01-22-49-4ac7b2248f5b511ff450d5fad311045b.gif)

Notice that the game stops after a win.

## Task 8: Checking every column
-----------------------------

```java
/**
 * Function name - checkWin
 * @param board (char[][])
 * @return count (int)
 *
 * Inside the function:
 *   1. checkRows(): Check every row for a straight X/O  (Task 7) 
 *   2. checkColumns(): Check every column for a straight X/O  (Task 8) <———
 *   3. checkLeft(): Check the left diagonal for a straight X/O  (Task 9).
 *   4. checkRight(): Check the right diagonal for a straight X/O  (Task 10).
 */
```
`checkColumns()`:  will check every column for a straight X or straight O:
-   The outer loop picks a column. The inner loop will index each row for that column.
-   When looking at the image below, think of `i` and `j`.

![](https://img-c.udemycdn.com/redactor/raw/article_lecture/2025-01-04_01-22-49-19a404569b97fe3c9046c9dcf9f66f07.gif)

A player wins if one of the columns results in a `count` of 3 or -3:

![](https://img-c.udemycdn.com/redactor/raw/article_lecture/2025-01-04_01-22-50-e6f52149196ab91929b68690dca1f2ad.gif)

Test every column before you move to Task 9.

## Task 9: Checking the left diagonal
----------------------------------

If none of the rows or columns result in a count of 3 or -3, reset the count to 0.

```java
/**
 * Function name - checkWin
 * @param board (char[][])
 * @return count (int)
 *
 * Inside the function:
 *   1. checkRows(): Check every row for a straight X/O  (Task 7) 
 *   2. checkColumns(): Check every column for a straight X/O  (Task 8) 
 *   3. checkLeft(): Check the left diagonal for a straight X/O  (Task 9). <———
 *   4. checkRight(): Check the right diagonal for a straight X/O  (Task 10).
 */
```
`checkLeft()`: will check the left diagonal for a straight X or O:
-   Do you see a pattern in the indices?
-   You don't need a nested loop. Use a single `for` loop.

![](https://img-c.udemycdn.com/redactor/raw/article_lecture/2025-01-04_01-22-50-1121224df3ddd1e4726e892263662dc0.gif)

**Output**:

![](https://img-c.udemycdn.com/redactor/raw/article_lecture/2025-01-04_01-22-50-b01d3ecd2aeec6409ada660ecee03fdd.gif)

## Task 10: Checking the right diagonal
------------------------------------

If none of the rows, columns, or left diagonal result in a win, reset the count to 0.

Now, check the right diagonal for a straight X or O.

```java
/**
 * Function name - checkWin
 * @param board (char[][])
 * @return count (int)
 *
 * Inside the function:
 *   1. checkRows(): Check every row for a straight X/O  (Task 7) 
 *   2. checkColumns(): Check every column for a straight X/O  (Task 8) 
 *   3. checkLeft(): Check the left diagonal for a straight X/O  (Task 9). 
 *   4. checkRight(): Check the right diagonal for a straight X/O  (Task 10). <———
 */
```

`checkRight():` will check the right diagonal for a straight X or O:

-   You don't need a nested loop. Use a single `for` loop.
-   The pattern here is a bit tricky:

    -   2 - **0** = **2**
    -   2 - **1** = **1**
    -   2 - **2** = **0**

Compare the bolded numbers from the hint to the indices below:

![](https://img-c.udemycdn.com/redactor/raw/article_lecture/2025-01-04_01-22-50-ff95b15640449d5f18919b6ba30841e6.gif)

**Output**:

![](https://img-c.udemycdn.com/redactor/raw/article_lecture/2025-01-04_01-22-50-4eae566ea2a3ea61f937136c46f4a8de.gif)

## Task 11: What if it's a tie?
----------------------------

If the game goes all nine turns and nobody wins, print: "it's a tie!".

## Task 12: Test your code!
------------------------

Test your code by verifying the output for:

-   straight row

-   straight column

-   left diagonal

-   right diagonal.

-   Tie.


If everything works, you have my sincere congratulations! Tic tac toe is not an easy project, and going through this challenge is a strong testament to your growth.

Good Luck!
----------
##### **Go From Zero to DevOps Master**: *[Java → Spring Boot → Docker → Kubernetes](https://rslim087a.github.io/zero-devops-roadmap/)*
