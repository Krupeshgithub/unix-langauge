# **Unix Shell Programming**

***Shell Types*** :

- In unix, there are two major types of shells 
    - Bourne Shell - If you are using a Bourne-type shell, the $ character is the default prompt.
    - C shell - If you are using a C-type shell, the % character is the default prompt.

- For starting any shell script file, you need to alert the system that a shell script is being started.

```sh
#!/bin/sh
```

> - It's called a **shebang** because the # symbol is called a hash, and the ! symbol is called a bang.

***Varibale in shell*** :

> variable_name=variable_value
```sh
$ NAME="Krupesh Patel" # (scalar variable.)
```
- *Acessing values* : 
 
    - To access the value stored in a variable, prefix its name with a dollar sign ($).

```sh
$ echo $NAME
```

- Note :
    - Read-only variables
    - After a variable is marked read-only, its value cannot be changed.
    - Script generates an error while trying to change the values.

```sh
$ NAME="KRUPESH PATEL"
$ readonly NAME
$ NAME="krupesh patel"
```

- Unsetting variables :

    - Unsetting or deleting a variable directs the shell to remove the variable from the list of variables that it tracks. Once you unset a variable, you can't access the stored value in the variable.

```sh
$ NAME="Krupesh Patel"
$ unset NAME
$ echo $NAME
```

**Variable Types**

> Local Variables :
- A local variable is a variable that is present within the current instance of the shell. It is not available to programs that are started by the shell. They are set at the command prompt.

> Environment Variables :
- An environment variable is available to any child process of the shell. Some programs need environment variables in order to function correctly. Usually, a shell script defines only those environment variables that are needed by the programs that it runs.

> Shell Variables :
- A shell variable is a special variable that is set by the shell and is required by the shell in order to function correctly. Some of these variables are environment variables whereas others are local variables.

***Special Variables*** :

- This is because those characters are used in the names of special unix variables.

> Input to the bash script is provided in the format:

```
./script.sh <input list>
```

| Special Variable |        Description
| ---------------- |:----------------------------------:|
|       $0         | The filename of the current script.
|       $n         | "n" refers to a positive number that represents the nth argument passed to the script. ex: $1 represents the first argument.
|       $#         | Represents the number of arguments passed to the script.
|       $*         | Represents all the arguments passed to the script.
|       $?         | Returns the exit status of the last command that was executed.       
|       $!         | Holds the process ID of the last background command.
|       $$         | Represents the process ID of the current shell.
|       $@         | Represents all the arguments passed to the script.


```sh
./script.sh This is the argument list.
```

```bash
#!/bin/bash
echo "Script name $0"

for ARGS in $@
do 
    let i=i+1
    echo "Argument $i is $ARGS"
done

echo "Parameter list: (individually) $@"
echo "Parameter list: (as a single list) $*"
echo "Total number of parameters $#"
echo "Process ID $$"
```

***Exit status ($?)*** :

The exit status of a command is a numerical value that is returned after the execution of the command. This numerical value indicates whether the command was executed successfully or not. As a rule of thumb, an exit status of 0 indicates success, and an exit status of 1 indicates failure.

```bash
echo "Executing echo command..."
if [$? -eq '0']
then 
    echo "The last command executed successfully" Exit status $?"
else 
    echo "The last command was unsuccessful: Exit status $?"
fi
```

***Array Variables*** :

- An array is a variable that can store values of the same data types. Each value in an array is indexed starting from index 0 for the first value. The difference between an array and a shell script array is that it supports values of all data types.

    - **Explicit Declaration** : Here, we declare the array and assign value to them.

```bash
$ declare -a
```
> Return all variables.

- Accessing Array Elements
```bash
$ declare $(variable name) || (set | grep $(variabel name))

$ echo $(variable name)

$ echo $(variable name[index]) # Specific indexing values.
```

- Loop
```bash
$ name=("krupesh" "rahul" "rekha")

$ for itr in $name; do echo $itr; done
```

- Slicing :
 
```bash
$ echo ${variable-name[@]:1:4}
```
> Syntax: ${variable-name[@||*]:0:3}

- Count :

```bash
$ echo ${#variable-name}
```

- Delete :
```bash
$ unset (variable-name)
```

- Replace Array Temporary :
```bash
$ echo ${variable-name/character/replacement}
```

***Unix Operators*** :

-  There are five basic operations that one must know to use the bash shell.

    1. Arithmetic Operators
    2. Relational Operators
    3. Boolean Operators
    4. Bitwise Operators
    5. File Test Operators

> Bourne shell didn't originally have any mechanism to perform simple arithmetic operations but it uses extenal programs, either **awk** or **expr**.

```bash
a=5
b=10
echo "a + b = $((a + b))" || echo "a + b = $(expr $a + $b)"
```

**Relation operators** :

```bash
a=100
b=10
if(( $a == $b )) || if[$a -eq $b]
then 
    echo "a and b are equal"
fi
```

**Boolean Operators**

```bash
echo "LOGICAL_AND = $((1 && 0))"
echo "LOGICAL_OR  = $((0 || 1))"
echo "LOGICAL_Neg = $((!0))"
```
