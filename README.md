Smart Sass Exam
===============

[Sass](http://sass-lang.com/) is a language that compiles into CSS. 
It supports may useful features, such as nesting, variables, imports, inheritance, mixins and more. 

In large projects with many Sass files, constantly compiling all the Sass files to CSS can be expensive during dev time.
**Your goal** is to create a 'Smart Sass' *node module* which, when run, will help to optimize the Sass compilation by deciding which files need to be compiled.

The module should receive an array of source directories/patterns as input, supporting the **glob/minimatch** patterns (representing where the Sass files are located), and a target directory root, which is where the css files are written to using the same patterns applied to the target root directory.

Your output should be an array of the files which need to be compiled.

###**Guidelines:**

>1. Although you do not need to actually compile the files, you should carefully read the [features supported by Sass](http://sass-lang.com/guide). 
>There may be features you need to specifically account for when deciding what to compile.
>2. The module can have dependencies. Use of utilities is encouraged (and likely necessary for a good solution). 
>That said, the module should be able to be run by itself without being dependent on a task runner such as grunt to run it.
>3. You can write the module either as a synchronous task or an asynchronous one. The choice is yours.
>  * If it's synchronous, it should return an array of the filepaths which need to be compiled by Sass.
>  * If it's asynchronous, it should also accept a callback, which will be called upon completion with an array of the filepaths as the argument to the callback.
> 4. Your submittd result should also wrap the module and log the result to the system console.
> 5. **Bonus points**: write it TDD style with good test coverage.


A **synchronous** version of the exported module should have the following signature:
```js
function smartSass(sourcePatterns, targetDirectoryRoot){
 var filesWhichNeedSass = [];
 // .. 
 // ..
 return filesWhichNeedSass;
}

```
-----
An **asyncronous** version of the exported module should have the following signature:
```js
function smartSass(sourcePatterns, targetDirectoryRoot, callback){
 // var filesWhichNeedSass = [];
 // ..
 // ..
 // when done:
 // callback(err, filesWhichNeedSass);
}
```
The callback should support the node-style callbacks in order to support error reporting.


#### Please also submit a **partial solution** if you have not completed it. A partial solution is better than none at all!
