# nlex
### Natural Language Executor 

A Command Line Framework for executing arbitrary commands, but not in a traditional command heirarchy, but in a graph-like manner. For example

```npm
command subcommand -option argument
```

In this example, all options must be in that specific order. But information is not in tree heirarchies in the human mind, but the graph topology is something much more generic, really, it's natural language. This project is rather primitive, but it is deterministic and to begin with it will ask you if the command is correct before you execute it. In this new framework, you can order the commands like the following:

```bash
subcommand argument command -option
```

Basically, it can be arranged anyway you would like, provided there is no ambiguity. In the above case, so long as no `subcommands` have the same name as `commands` and `argument` is not a `command` or a `subcommand` then the command line can interpret the `command` and `subcommand` as keywords. The argument is not a keyword, so will be treated as an argument, and the option is prefaced with a `-`. If one of these conditions fails, and the command is ambiguous, you will be prompted to clarify which command you mean. But this will occur only in the fairly rare case that an argument is also a keyword.
