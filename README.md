# Thoth

<p align="center">
  <a href="LICENSE"><img src="https://img.shields.io/badge/License-MIT-4c566a" alt="License: MIT"></a>
</p>

Thoth contains the operating directives I use with AI coding agents.
The directives live in [`AGENTS.md`](AGENTS.md).

The file defines how an agent checks instructions, uses available tools, changes files, and maintains project documentation.
The file does not prescribe a programming language or application framework.

## Directives

- The agent checks project resources before generating a solution.
- The agent checks available skills and tools before choosing an approach.
- The agent follows an explicit order when instructions conflict.
- The agent verifies claims against files, tool output, or execution results.
- The agent uses Git and progress records to preserve work across sessions.
- The agent checks its work against named failure categories.
- The agent maintains a hierarchy of project and directory instructions.
- The agent limits changes to the requested scope.

## Use

Copy `AGENTS.md` into the root of your project.
Configure your coding agent to read that file.
The configuration method depends on the agent.

Read the directives before adopting them.
Adapt project requirements and local constraints to your repository.
The file provides instructions; the agent must still follow them correctly.

## Documentation structure

Thoth includes a documentation hierarchy based on [DOX](https://github.com/agent0ai/dox).
The root `AGENTS.md` owns project requirements.
Directory `AGENTS.md` files own requirements for their directories.
The parent file indexes its child files.

Sections 13 and 14 describe this structure and its maintenance requirements.

## Skills

Thoth defines operating rules for the agent.
A skills framework supplies procedures for specific tasks.
Thoth can work alongside [Superpowers](https://github.com/obra/superpowers) or another skills framework.

## Version

`AGENTS.md` declares version `1.3.0`.

## License

The [MIT license](LICENSE) covers this project.
