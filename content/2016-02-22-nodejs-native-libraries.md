Title: NodeJS Native Libraries
Date: 2016-02-22 16:56:47
Category: Programming
Tags: nodejs, crypto
Authors: Joshy Cyriac


I lost a day trying to find out what causes this error:
`error:06065064:digital envelope routines:EVP_DecryptFinal_ex:bad decrypt`

The error was thrown when the server tried to parse a encrypted JS array. The application was running NodeJS version 0.12.7 and the generation was done with NodeJS version 4.2.1.

First guess was that it is a runtime problem. So after running both with 0.12.7 the problem still existed. Google results poped up, showing there was a change between NodeJS 0.8 and 0.10, both version which I am not running.

As it turns out the library which we are using([serializer](https://github.com/AF83/node-serializer)) is using the `crypto` module from NodeJS. This is compiled against the NodeJS installation. The solution was, that is not sufficient to run both version on 0.12.7 but also to remove the installed node modules and install them *new* with version 0.12.7.


