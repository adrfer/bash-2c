# Bash Best Practices
A bunch of bash tips and tricks topped with a preferred scripting style.

Ideas tested in `GNU bash 3.2.57`.

--

So, here are my 20 cents:

- Use the `#!/usr/bin/env bash` hashbang as the first line of the script
- Use `chmod +x` to make a script executable
- Use `.sh` or `.bash` extensions only if the file is meant to be included/sourced
- Check for the number of arguments `${#}` provided to the script
- Check if a file and/or a directory exists before accessing it
- Provide a usage description in case users need help or misuse the script
- Wrap variables and parameter expansions in curly braces `{` and `}`
- Use `"double quotes"` for arguments that contains expansions such as `"${variable}"` or `"$(command)"`
- Use `'single quotes'` for everything else and when to make sure that everything in quotes remains literal
- Use builtin parameter expansions rather than external functions
- Use lowercase for variable names unless exported to the environment
- Use uppercase for environment variables
- Use `mktemp` to create temporary files and always cleanup after with a `trap`
- Use `&>/dev/null` to mute command outputs and tell users what went wrong in a more friendly way
- Skip test for output `[[ ... ]]` in if-expressions if test for exit code is required
- Avoid [obsolete and deprecated syntax](http://wiki.bash-hackers.org/scripting/obsolete)

--
Hey, looking for some bash badassery? Check [bash-oh-my](https://github.com/adrfer/bash-oh-my).
