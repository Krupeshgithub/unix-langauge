# Unix langauge

### ***About*** :
`sh` is a command langauge interpeter that executes command read from a command line string.

The boume shell was developed in 1977 by stephen bourne at AT&T's Bell Labs.

### ***Features*** : 
- The shell may be used interactively or non-interactively.
- Commands may be executed synchronously or asynchronously.

***Command substitution*** :
```
~/echotest.sh
```
```
echo "The name of this script is `basename $0`."
```

***Metacharacters*** :

- Metacharacters have a special meaning in unix. For example, * and ? are metacharacters. We use * to match 0 or more character, a question mark(?) matches with a single character.

```
$ ls ch*.doc
```

<pre>
.profile - The Bourne shell (sh) initialization script.
.kshrc - The Korn shell (ksh) initialization script.
.cshrc - The C shell (csh) initialization script.
.rhosts - The remote shell configuration file.
</pre>

```
~$ ls -a
```
- *Single dot(.)* - This represents the current directory.
- *Double dot(..)* - This represents the parent directory.

***Standard Unix Strems*** :
- **STDIN ``Standard Input 0``** - The Unix program will read the default input from `STDIN`.

- **STDOUT ``Standard Output 1``** - The Unix program will write the default output at `STDOUT`.

- **STDERR ``Standard Error 2``** - The Unix program will write all the error messages at `STDERR`. 

***Chmod (Change mode)*** :

| Number | Octal Permission Representation   | Ref |
| -------|:---------------------------------:| ---:|
| 0      | No permission                     | --- |
| 1      | Execute permission                | --x |
| 2      | Write permission                  | -w- |
| 3      | Execute and Write permission      | -wx |
| 4      | Read permission                   | r-- |
| 5      | Read and execute permission       | r-x |
| 6      | Read and write permission         | rw- |
| 7      | All permission                    | rwx |

***Environment variable*** :

```bash
$TEST="Unix Programming"
$echo $TEST
```

- Note that the environment variable are set without using the `$` sign but while accessing them we use the `$` sign as prefix. 

- When you log in to the system, the shell undergoes a phase called `initialization` to set up the environments.

***The .profile file*** :
- The file /etc/profile is maintained by the system administrator of your Unix machine and contains shell initialization information required by all users on a system.

- The file .profile is under your control. You can add as much shell customization information as you want to this file.

***Basic utilities*** :

- `Print files` : pr options(s) filename(s)

<pre>
$ cat food
Sweet Tooth
Bangkok Wok
Mandalay
Afghani Cuisine
Isle of Java
Big Apple Deli
Sushi and Sashimi
Tio Pepe's Peppers
...
</pre>

```bash
$ pr -2 -h "Restaurants" food
```

***pipe (|)*** :
- When a program takes its input from another program, it performs some operation on that input, and writes the 
result to the standard output. It's referred to a filter.

***grep*** :

- The grep command searches a file or files for lines that have a certain pattern.

```bash
$ grep pattern file(s)
```

- `grep (globally search for a regular expression and print all lines containing it.)`

```bash
$ ls -l | grep "Jun"
```

```bash
$ ls -l | grep -i "john.*aug"
```

***sort*** :

- `sort` command arranges lines of text alphabetically or numerically.

<pre>
$ ls -l | grep "Jun" | sort +4n

-rw-rw-r--  1 mehul mehul         0 Jun 16  2022 untitled.txt
drwxr-xr-x  3 mehul mehul      4096 Jun  8  2022 aws
drwxr-xr-x  9 mehul mehul      4096 Jun  5  2022 Python-3.9.1
-rw-rw-r--  1 mehul mehul  47091419 Jun 15  2022 awscliv2.zip
</pre>

> +4n skips four fields (fields are separated by blanks).
