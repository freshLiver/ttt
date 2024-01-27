# ttt

An implementation of [tic-tac-toe](https://en.wikipedia.org/wiki/Tic-tac-toe) in C,
featuring an AI powered by the [negamax](https://en.wikipedia.org/wiki/Negamax) algorithm.

This program operates entirely in the terminal environment.
Below is its appearance as it awaits your next move:
```
 1 |  ×
 2 |     ○
 3 |
---+----------
      A  B  C
>
```

To execute a move, enter `[column][row]`. For example:
```
> a3
```

Press Ctrl-C to exit.

## Game Rules
The winner is determined by the first player who successfully places three of their marks in a row, whether it be vertically, horizontally, or diagonally, regardless of the board size.

For these two 4x4 board games as examples,

```
 1 |  ×  ×
 2 |     ○  ×
 3 |     ○
 4 |     ○
---+------------
      A  B  C  D
>
```

The player "○" wins the game since he placed his marks in a row vertically (B2-B3-B4).

```
 1 |  ×  ×  ○
 2 |  ×  ○  
 3 |  ○  
 4 |     
---+------------
      A  B  C  D
>
```

The player "○" wins the game since he placed his marks in a row diagonally (A3-B2-B1).

## Code Formatting Check

To enable the code formatting check, you need to install clang-format ([version >= 12](https://clang.llvm.org/docs/ClangFormatStyleOptions.html#statementattributelikemacros)), and configure your local repository with:

```bash
git config --local core.hooksPath .githooks
```

Then, when there is any format error in your commit, your commit will be aborted with some messages like:

```diff
+++ expected coding style
@@ -323,7 +323,8 @@ int get_input(char player)
     return GET_INDEX(y, x);
 }

-int main() { // format error 1
+int main()
+{  // format error 1
     char *table = malloc(sizeof(char) * N_GRIDS);
     if (!table)
         return -1;
@@ -332,7 +333,7 @@ int main() { // format error 1
     char ai = 'O';

     while (1) {
-        char win = check_win(table   ); // format error 2
+        char win = check_win(table);  // format error 2
         if (win == 'D') {
             draw_board(table);
             printf("It is a draw!\n");
Code format check: Failed, commit aborted...
```

## Reference
* [Mastering Tic-Tac-Toe with Minimax Algorithm in Python](https://levelup.gitconnected.com/3394d65fa88f)
* [tic-tac-toe](https://github.com/jserv/tic-tac-toe): tic-tac-toe game for terminal I/O.
