# tools

Python tools for HOI4 modding. The parser, converters, checkers.

Each tool in its own folder. A tool folder holds the code, its tests, and a short README saying what it does and how to run it.

The parser library itself lives in its own repo, `Hogathos/hoi4.py`. Tools here use it, they do not duplicate it.

Test-first for new behavior. Write the failing test, Charles reviews it, then implement.
