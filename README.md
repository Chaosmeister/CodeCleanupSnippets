# CodeCleanupSnippets
This is a collectionn of snippets to cleanup codebases


## Regex

### Find functions that return const but non-pointer/non-reference values

`^const [^*&=]*\(`

#### remark: also finds const variable declarations with parentheses definition
