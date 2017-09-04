# Contributing code to [Suran Systems, Inc.'s](http://www.suran.com) repositories

## How to contribute
Pull requests are more than welcome! If submitting a change in the Omnis code and you're running Omnis Studio version 8.1 or later, simply update the `src/[project]` directory with a JSON export of your library and submit the pull request. If your pull request is approved, the maintainers will manually merge your changes into the libraries under `lib`.

If you're running a version of Studio earlier than 8.1, please submit a pull request with your updated library and a README.txt file noting the changes. If your pull request is approved, the maintainers will manually merge in your changes the supported libraries and build a new JSON export under `src`.

## Conventions
Suran uses several coding conventions that may be foreign to some Omnis developers. When contributing, please try to adhere to these standards.

### Protected methods and variables in Omnis
Omnis does not natively offer a protected method or variable, which a method or variable that can be accessed by the current class or its subclasses only. In the course of adding unit tests to Omnis code, we found a need to be able to protect code like a private method does, but still invoke it from a test class, like a public method. We use an underscore to indicate a method or variable is protected:
 * `$public`
 * `$_protected`
 * `private`

### Hungarian notation
We prefix Omnis classes and variables to indicate their type, scope, and purpose in the application. Bash and Powershell scripts are less strict in following these prefixes.

#### Variables
Scope | Prefix
-------------- | ------
Task | t
Class | c
Instance | i
Local | l
Parameter | p

Type | Prefix
------------- | ------
Binary | [bn]
Boolean | b
Character | c
Field Reference | f[prefix for the destination variable's expected type], e.g. pfcName
Integer | i
Item Reference | ir
List | l
Number | n
Object Reference | or
Object | o
Picture | [p]
Row | r

#### Classes
Type | Prefix
---------- | ------
Code | c
File | f
Menu | m
Object | o
Query | q
Remote Form | rf
Remote Task | rt
Report | r
Schema | s
Search | (we don't use these) 
Table | t
Task | k
Toolbar | b
Windows | w

Module | Prefix
---------- | ------
Level 0 Superclass (does not require a user session in the application) | 0
Level 1 Superclass (expect an authenticated user session in the application) | 1
Level N Superclass (targeted superclass for a specific program area) | N
General | g
Developer | d
Smart field designed to represent data via a subwindow's `$dataname` property | _ 

**NOTE**: Module prefixing is used internally in our commercial products. While we don't require these prefixes for open-source projects, you may encounter these prefixes. They're noted here to explain what they mean.

#### Examples
* An object with a character instance variable would be `oFoo.icBar`.
* A smartfield for showing text in a console format would be `wg_Console`.

### Quotes
Please use double quotes to quote literal values in Omnis code. In scripts, double-quote any variable and wrap them in `${}`
 to handle proper expansion.