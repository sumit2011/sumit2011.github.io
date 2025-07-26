# Node js

***Navigation system works on the concept of linked list.***
<!--more-->

{{< admonition type=note title="Note" open=true >}}
_Use the table of contents to navigate to the portion that you are interested in._
{{< /admonition >}}

## 1. Introduction:
Node js is a runtime environment for java script. we can run js code outside the browser by using nodejs.
Ryan Dahl embedd the v8 chromium engine with c++. Which allows to run js. we can create webservers in js language. Node js is not a framwork nor a library.
It is open-source cross platform.


## Installation and Setup
go to nodejs.org. There are two option LTS(long term support or stable) and current(beta version).
even versionaing for the stable release and odd versioning for testing or beta release.

to check version 
`node --version`

## npm
Node package manager, when we install node js it automatically installed npm. it manages the packages which can be installed and maintained and update.

## 1st node js program: hello world
how to run js file
`node hello.js`
### npm init
it initialise the project with proper configuration. it creates the package.json file which contains all the package with version and meta data.

## Modules in node js
every js file is a module. In production there are several funcions we have to create several files to maintain the code effectively.There will be so many such js files.

### how to include pakage
using require function we can include external pakages or modules.
`const math = require("math");`
it will find pakage in built-in package or module.

`const math = require("./math");`
it will find pakage in the current directory.

## File handling in nodejs
it simply means creating a file and read the file. There is a built-in function to handle the file is `fs`

ex

const fs = require("fs");

// sync
fs.writeFileSync("./test.txt","hey there"); // it will create a file with name test.txt with content hey there.

//async only diff is it contain callback function
fs.writeFile("./test.txt", "hello world", (arr)=>{})

const result = fs.readFileSync("./contacts.txt","utf-8");

//async
fs.readFile("./contact.txt", "utf-8", (err,result)=>{
    if(err){
        console.log("error",err);
    }
    else{
        console.log(result);
    }
})

fs.appendFileSync("./test.txt", `hey there`);

## Node js architecture

