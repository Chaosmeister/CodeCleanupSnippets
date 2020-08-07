# Code cleanup snippets
This is a collectionn of snippets to cleanup codebases


## Regex:

### Find functions that return const but non-pointer/non-reference values

`^const [^*&=]*\(`

#### Languages:
c++

#### Remark:
This also finds const variable declarations with parentheses definition, so needs manual labor to check results

#### Example:
```cpp
const float f(); // unnecessary const return value
const std::string s(""); // OK - const variable definition
```

### Find C-Style casts

`\)\w` // cast is next to variable  
`\) \w` // with-whitespace variant

#### Languages:
c++

#### Remark:
Taken from: https://stackoverflow.com/a/2593192/2916264
Works surprisingly well but still finds false results and only finds casts where the `)` is next to the variable.
The with-whitespace variant returns even more false results.

#### Example:
```cpp
const float f = (float)x; // codesmell
```
