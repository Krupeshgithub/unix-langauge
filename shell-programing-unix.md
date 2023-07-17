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

