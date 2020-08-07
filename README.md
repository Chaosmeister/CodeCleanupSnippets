# CodeCleanupSnippets
This is a collectionn of snippets to cleanup codebases


## Regex

### Find functions that return const but non-pointer/non-reference values

`^const [^*&=]*\(`

#### remark:
also finds const variable declarations with parentheses definition, so needs manual labor to check results

#### example:
`const float f(); // unnecessary const return value`
`const std::string s(""); // OK - const variable definition`
