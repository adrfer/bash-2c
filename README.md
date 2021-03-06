# Bash 2c
A bunch of bash tips and tricks topped with a preferred scripting style.

Ideas tested against `GNU bash 3.2.57`.

## History

#### Command Recall
- `!!`: Recall the last command (e.g. !! or sudo !!)
- `!n`: Recall the nth command (e.g. !234)
- `!string`: Recall the most recent command starting with _string_ (e.g. !cd)
- `!?string`: Recall the most recent command containing _string_ (e.g. !?git)
- `^string1^string2`: Replace _string1_ with _string2_ on last command (e.g. cat /etc/hosst, ^hosst^hosts)

#### Argument Recall
- `:^`: Get the first argument of a command (e.g. ls !cp:^ or ls !!:^)
- `:$`: Get the last argument of a command (e.g. ls !cp:$ or ls !!:$)
- `:n`: Get the nth argument of a command (e.g. ls !cp:2 or ls !!:2)
- `:*`: Get all arguments of a command (e.g. ls !cp:\* or ls !!:\*)

#### Search and Replace
- `/string` or `Ctrl-r`: Search history backward for a command matching _string_
- `?string` or `Ctrl-s`: Search history forward for a command matching _string_

## Shortcuts

- `Tab`: Auto-complete file and folder names
- `Ctrl-a`: Move to the beginning of the line
- `Ctrl-e`: Move to the end of the line
- `Alt-f` or `Alt-right arrow`: Move cursor forward one word
- `Alt-b` or `Alt-left arrow`: Move cursor backward one word
- `Up arrow` and `Down arrow`: Move through recent commands
- `Ctrl-l`: Clear the terminal window
- `Ctrl-u`: Clear the line before the cursor
- `Ctrl-k`: Clear the line after the cursor
- `Ctrl-y`: Recall line deleted by Ctrl-u
- `Ctrl-w`: Delete the word before the cursor
- `Ctrl-c`: Cancel the current command
- `Ctrl-z`: Put whatever is running into a suspended background process
- `Ctrl-r`: Search through previously commands in history
- `Ctrl-d`: Exit the current shell
 
## Scripting

- Use the `#!/usr/bin/env bash` hashbang as the first line of the script
- Use `chmod +x` to make a script executable
- Use `.sh` or `.bash` extensions only if the file is meant to be included/sourced
- Use `"${#}"` to check for the number of arguments provided to the script
- Check if a file and/or a directory exists before accessing it
- Provide a usage description in case users need help or misuse the script
- Wrap variables and parameter expansions in curly braces `{` and `}`
- Use `"double quotes"` for arguments that contain expansions such as `"${variable}"` or `"$(command)"`
- Use `'single quotes'` for everything else and when to make sure that everything in quotes remains literal
- Use [builtin parameter expansions](https://www.gnu.org/software/bash/manual/html_node/Shell-Parameter-Expansion.html) rather than external functions
- Use lowercase for regular variable names, all uppercase are for environment variables only
- Use `mktemp` to create temporary files and always cleanup after with a `trap`
- Use `\command` to bypass an alias attributed to `command`, e.g. use `\ls` for the default `ls`
- Use `>/dev/null 2>&1` to mute command outputs and tell users what went wrong in a more friendly way
- Skip test for output `[[ ... ]]` in if-expressions if test for exit code is required
- Prior to iterating over a sequence, set the `IFS=$'\n\t'`, and `unset IFS` afterwards
- Use [shellcheck](https://github.com/koalaman/shellcheck) to make your scripts more robust

##
**Note**: Remember that `man bash` is always at your fingertips.

##
Hey, looking for some bash badassery? Check out [bash-oh-my](https://github.com/adrfer/bash-oh-my).

Interested in tuning your terminal profile? Take a look at [terminal-oh-my](https://github.com/adrfer/terminal-oh-my).
