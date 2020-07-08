# odin-ast-printer
AST printer for the Odin language

Uses the AST from the builtin parser in the core library to print the code.
Allows for meta programming, such as code insertion based on certain attributes on procs.

## Useage
```odin
package test

import "ast_printer"
import "core:strings"

main :: proc() {
	path = "some_path/some_file.odin";

	sb := strings.make_builder();
	defer strings.destroy_builder(&sb);

	ast_printer.print_ast(path, &sb);
	// The printed AST is now in the Builder
}
```

## Current status
At the moment the AST printer is about 90% done.
There are a couple of errors within the builtin parser itself, which I've covered in an [Issue](https://github.com/odin-lang/Odin/issues/628).
The long term plan is to have a complete compiler frontend in the core library eventually.
\
Some newer features and syntax things, that have already been added to the C++ compiler, are also missing from the builtin parser at the moment.