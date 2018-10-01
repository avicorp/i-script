# About

i-script help you set and use scripts in linux or mac. It doing that by very simple scripts:

    $ i-script
    List of i-scripts:
    i-addScript - Grant execution permission to the file (only for the user) and copy to usr/local/bin.
    i-dockerClean - Clean the exited docker containers.
    i-dockerCleanImages - Clean the old and unused docker images.
    i-newScript - read script from the user, build new script file and set it.
                    [-d | --description description]  - set the new script description (the result of -h paramter.
                    [-name file-name]                 - set the new script name
    i-scripts - Present the available scripts in usr/local/bin, from the pattern i-[script name].
    i-updateScripts - Copy files from the pattern i-[script name] to: /usr/local/bin from the current directory.
                    [-g]           - Run git pull.
                    [-f file-name] - Copy specific file to: /usr/local/bin.

# Getting started

run:

    git clone https://github.com/avicorp/i-script.git
    cd i-script
    chmod u+x istart
    ./istart

run:

    i-scripts //to see the scripts availebel

Can be run from every where.

## Add new script

Create script file, the name need to look like this: i-[mynewscript]

then run:

    i-addScript -f ./i-[mynewscript]

## Create new script

You can set new script file by running i-newScript.
This nice script will create the basic format and name for the code you want to run as a script.

    $ i-newScript -name i-printThreeLine -d 'echo three args in three line.'
    -- Write the script you want to set (close the editor by '-'):
    1: echo $1
    2: echo $2
    3: echo $4
    4: -
    -- Close the script editor? [y/n [y]]: n
    -- Select line for edit? [line number [new line]]: 3
    -- Fix the script (close the editor by '-'):
    3: echo $3
    4: -
    -- Close the script editor? [y/n [y]]:

    -- This is the new Script:

```bash
#!/bin/bash

description=$'i-printThreeLine - echo three args in three line.'

usage()
{
    echo "$description"
}

case $1 in
    -h | --help)    usage
                    exit
esac

echo $1
echo $2
echo $3
```

    -- Set the script? [y/n [y]]:
    Script: ./i-printThreeLine was added

Test the result:

    $ i-printThreeLine -h
    i-printThreeLine - echo three args in three line.

    $ i-printThreeLine 'first line' 'second line' 'third line'
    first line
    second line
    third line

## Update the script

run:

    i-updateScripts -f i-[mynewscript]

or run:

    i-updateScripts // update all the scripts in the current directory

scripts = files from the pattern i-[scriptname].

in case of git folder, you can run:

    i-updateScripts -g

## Contribution

Feal free to add new scripts by Pull request.