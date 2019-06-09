# test-prlint

Repo to use when testing PRLint Bot.

PRLint checks that your PR abides by team conventions.

The root directory of your repo should contain a .prlintrc file.

The .prlintrc file should contain a field called `checks`.

The `checks` object may contain the following fields: `commit`, `pr`.

The `commit` object contains checks that should be performed on the commit that triggered the check.

The `pr` object contains checks that should be performed on the pull request that triggered the check.

Each check is a key-value pair where the key is the name of the check to perform and the value is the (JavaScript) script to be executed for that check.

If the script evaluates to true then the check passes. If not, the check fails.

The script can be either a string or an array of strings. If the script tag is a string it is expected to be an expression to be evaluated, not a return statement; i.e. it is not expected to have the return keyword. If the script tag is an array of strings, each array element will be treated as a line of code, and executed without modification; i.e. somewhere in those lines of code there is expected to be a return statement.
