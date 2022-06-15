#1 The process of debugging my code

(1). To get the columns of the nested list,
we can use expression like this:
```
for j in range(len(board)):            
     column = [rows[j] for rows in board]
```


(2). The use of nested list slicing
I just realized that expression such as 'array[i:j][m:n]' is wrong
Only after importing numpy and convert list to array can we use this

```
for n in range(3):
     sub_box=[array[i:j] for array in board[m:n]]
```







