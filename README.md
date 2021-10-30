# PSR-12 Strict Coding Standard

This specification extends and expands [PSR-12](https://www.php-fig.org/psr/psr-12/),
the extended coding style guide and requires adherence to [PSR-1](https://www.php-fig.org/psr/psr-1),
the basic coding standard.

Contributors have different coding styles and so do the maintainers. During code reviews there are regularly
discussions about spaces and alignments, where and when was said that a function needs to be imported. And
that's where this coding standard comes in: To have internal consistency in a component and between components.

## Installation

Install the module via composer by running:

````bash
composer require --dev devbeta/psr12-strict-rules
````

## Usage

Create file `phpcs.xml` on base path of your repository with this content:

````xml
<?xml version="1.0" encoding="UTF-8"?>
<ruleset name="Coding standard"
         xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
         xsi:noNamespaceSchemaLocation="vendor/squizlabs/php_codesniffer/phpcs.xsd">
    <description>PSR-12 strict coding standard</description>

    <arg name="colors"/>
    <arg name="cache" value=".phpcs.json"/>
    <arg name="extensions" value="php"/>
    <arg name="parallel" value="80"/>

    <arg value="p"/>

    <rule ref="PSR12StrictRules"/>

    <file>config</file>
    <file>src</file>
    <file>tests</file>
</ruleset>
````

You can add or exclude some locations in that file.
For a reference please see: [Annotated Ruleset](https://github.com/squizlabs/PHP_CodeSniffer/wiki/Annotated-Ruleset)

## Coding Style Guide

### Basic Coding Standard

- Code MUST follow all rules outlined in PSR-12.

### Arrays

- All values in multiline arrays must be indented with 4 spaces.
- The short array syntax MUST be used to define arrays.

### Classes

- There MUST NOT be duplicate class names.
- Checks the declaration of the class and its inheritance is correct.
- The file name MUST match the case of the terminating class name.
- For self-reference a class lower-case `self::` MUST be used without spaces around the scope resolution operator.

### Code Analysis

- The final keyword on methods MUST be omitted in final classes.
- Detects unnecessary overridden methods that simply call their parent.

### Control Structures

- Verifies that control statements conform to their coding standards.
- Ensure multi-line `if` conditions are defined correctly.

### Formatting

- There MUST be one whitespace after a type casting operator.
- There MUST be one whitespace after unary not.
- If an assignment goes over two lines, ensure the equal sign is indented.

### Functions

- Ensure single and multi-line function declarations are defined correctly.

### Metrics

- Checks the cyclomatic complexity (McCabe) for functions.
- Checks the nesting level for methods.

### Naming Conventions

- Checks that abstract classes are prefixed by Abstract.
- Ensures method and functions are named correctly.
- Checks that interfaces are suffixed by Interface.
- Checks that traits are suffixed by Trait.

### Operators

- The `&&` and `||` operators SHOULD be used instead of `and` and `or`.

### PHP

- The backtick operator MUST NOT be used.
- Deprecated PHP functions MUST be avoided.
- The PHP `goto` language construct SHOULD NOT be used.
- Alias functions SHOULD NOT be used.
- Throws an error or warning when any code prefixed with an asperand is encountered.
- Checks that the `strict_types` has been declared.
- The constant `PHP_SAPI` SHOULD be used instead of the `php_sapi_name()` function.
- The `global` keyword MUST NOT be used.
- PHP function calls MUST be in lowercase.
- Non executable code MUST be removed.

### Scope

- The pseudo-variable `$this` MUST NOT be called inside a static method or function.

### Strings

- Checks that two strings are not concatenated together; suggests using one string instead.
- Makes sure there are no spaces around the concatenation operator.

### WhiteSpace

- Check & fix whitespace on the inside of arbitrary parentheses.
- Verifies spacing between the spread operator and the variable/function call it applies to.
- Checks that object operators are indented correctly.
- Checks that the closing braces of scopes are aligned correctly.
- Checks the separation between functions and methods.
- There MUST be a single space after language constructs.
- There MUST NOT be any white space around the object operator UNLESS multilines are used.
- Verifies that class members are spaced correctly.
- Ensure there is no whitespace before/after an object operator.
- Verifies that operators have valid spacing surrounding them.
- There MUST NOT be a space before a semicolon. Redundant semicolons SHOULD be avoided.
