include` and `require`

# `include` and `require`

* The `include` (or `require`) statement takes all the text/code/markup that exists in the specified file and copies it into the file that uses the include statement.

* The `include` and `require` statements are identical, except upon failure:

	* `require` will produce a fatal error (`E_COMPILE_ERROR`) and stop the script

	* `include` will only produce a warning (`E_WARNING`) and the script will continue

* Syntax

	* `include 'filename'`;

	* `require 'filename'`;

#### Use `require` when the file **is required** by the application.

#### Use `include` when the file is **not required** and application should continue when file is not found.