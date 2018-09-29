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