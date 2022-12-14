# functional-tools
Commands to make shell scripting more like functional programming.

These aren’t even written in a functional language; they’re just scripts in python3.

Included so far:
- `lmerge`: like the `zip` function, but for each line takes a tab-separated list of space-separated lists.
- `lsep`: the inverse of `lmerge`.

Libraries used:
- `sys`
- `itertools`
- `argparse`

Basic example:
```
$ echo "1 2 3\t2 3 4\n3 4 5\t56 20 50 60 70\t11 12 13 15\n111 112 113" > tmp
$ cat tmp
1 2 3	2 3 4
3 4 5	56 20 50 60 70	11 12 13 15
111 112 113
$ cat tmp | lmerge
1:2 2:3 3:4
3:56:11 4:20:12 5:50:13 :60:15 :70:
111 112 113
$ cat tmp | lmerge | lsep
1 2 3	2 3 4
3 4 5  	56 20 50 60 70	11 12 13 15 
111 112 113
```

More examples to follow.
