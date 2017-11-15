# [:house: Feni Batch Home Page](http://poloey.github.io/feni)

# Class 31 
Today we've made a command line Application using php. Which will generate our mvc project and we can create route, view, and controller in command line

## documentation for mvc.php file.
mvc.php is a command line Application. Which actually help you to bootstrap your php project quicker.    
first download mvc.php file from github. Make a folder and keep `mvc.php` file in this folder. open this folder in your terminal.   
* To bootstrap  your project command will be `php mvc.php`.
* To create a route command will be `php mvc.php r:<routeName>`
* To create a view command will be `php mvc.php v:<routeName>`
* To create a controller command will be `php mvc.php c:<routeName>`
* To create a route, view and controller command will be `php mvc.php rvc:<routeName>`   
Hope it will help you much in your future. 


## How can you make this command line Application ? Inorder to make a command line Application you go through below functions which will help you to make your very own command line Application.

### explode function
explode function split a string into array. It takes 2 parameter. one is `delimiter`, two is string you wan t to explode.
~~~php
explode(delimiter, string)
~~~
suppose `sumon mujib sarwar` is a string. We can make this string into array where delimiter will be empty space ` `.
~~~php
// here we are convert string into array where delimiter is space.
$friends_string = 'sumon mujib sarwar';
$friens_array = explode(' ', $friends_string);


// here we are convert string into array where delimiter is comma and space
$friends_string = 'sumon, mujib, sarwar';
$friens_array = explode(', ', $friends_string);
~~~
### `list` function 
`list` function help use quicker way assign some variable from array. From the following array we destructing array into variable  via older approach.
~~~php
$friends = ['sumon', 'sarwar', 'tanim'];
$friends1 = $friends[0];
$friends2 = $friends[1];
$friends3 = $friends[2];
~~~
we make assign 3 variable 3 separate line. We can do things in one line using `list` function.
~~~php
$friends = ['sumon', 'sarwar', 'tanim'];
list($friends1, $friends2, $friends3) = $friends;
~~~
### Heredoc   
For larger block of string we are using heredoc. Heredoc start with `<<<` and followed by a identifier. closing identifier should be written without any indentation. In between starting and ending identifier we will write our string. Heredoc support string interpolation
~~~php
$content = <<<TEXT
Hello world 
TEXT;
~~~
Here we keep `TEXT` as identifier. You can write anything as identifier. 
~~~php
$name = 'Shibu deb polo';
$content = <<<ANYTHING
Hello, my name is $name.
ANYTHING;
// output will be 
Hello, my name is Shibu deb polo.
~~~
### Nowdoc   
Nowdoc and heredoc more or less same only different is nowdoc not support string interpolation starting identifier should be encapsulate with `'` quote.

~~~php
$name = 'Shibu deb polo';
$content = <<<'ANYTHING'
Hello, my name is $name.
ANYTHING;
// output will be 
Hello, my name is $name.
~~~

## file handling in php
File handling in php is very easy. It has very easy syntax for manipulating files. suppose in real life in order to write something inside a file what we generally do? 
* open a file
* write something in this file
* close this file

### file open
in php to open file we use `fopen`. which takes 2 arguments. first argument is, which file I want to open. 2nd argument is, what is the reason behind for opening this file. say we open file for reading we will give `r`. If we open file for writing we will give `w`. If we open file for appending new line we will give `w`. If the file you want to open is not exists it will create this file and open it for you.
~~~php
$file = fopen('hello.txt', 'w');
~~~
Here we open `hello.txt` file for writing content inside.
### writing content inside file
for writing content inside file we will use `fwrite` function. 
~~~php
fwrite($file, 'hello world from dhaka');
~~~
Here I wrote  `hello world from dhaka` inside my `hello.txt` file.

### closing file
After writing down we have to close our file using `fclose` function.
~~~php
fclose($file);
~~~

### make a directory
Using `mkdir` function we can create a folder in php
~~~php
mkdir('new-folder');
~~~
here we created `new-folder`.

### checking file or folder exists or not
Using `file_exists` function we can check whether file or folder exists or not. So file_exists function will give use a boolean value. 
~~~php
// checking new folder exists or not
file_exists('new');
// checking hello.txt file exists or not
file_exists('hello.txt');
~~~

### argv array for command line input
all command line input will be stored inside argv array in php. 
suppose in terminal I typed `php hello.php` in this case `argv`  first element will be `hello.php`. suppose in terminal I typed `php hello.php dhaka`. In this case `argv` first element will be `hello.php` 2nd element will be `dhaka`.

~~~php
//in terminal
php mvc.php c:index

//inside mvc.php
$filename = $argv[0] // will return mvc.php
$command = $argv[1] // will return c:index
~~~

If you understand today class Hope you will make lot of interesting command line Application using PHP. like `mvc.php` 


















































