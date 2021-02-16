# `nix-linter`

Micro editor compatible fork. Output is reversed for easier parsing:

```
filename:line:column:message
```

If anyone knows more about LUA and Micros parsing (You probably do), 
please attempt to contribute directly to Micro at
https://github.com/zyedidia/micro

`nix-linter` is a program to check for several common mistakes or stylistic
errors in Nix expressions, such as unused arguments, empty let blocks,
etcetera.

## Usage

First, setup cachix:

```sh
cachix use nix-linter
```

Then clone the repo and `cd` into it:

```sh
git clone https://github.com/Synthetica9/nix-linter
cd nix-linter
```

Finally, you can run the application with:

```sh
$(nix-build -A nix-linter)/bin/nix-linter --help

```

```
The nix-linter program

nix-linter [OPTIONS] [FILES]

Common flags:
  -W --check=ITEM       checks to enable
  -j --json             Use JSON output
  -J --json-stream      Use a newline-delimited stream of JSON objects
                        instead of a JSON list (implies --json)
  -r --recursive        Recursively walk given directories (like find)
  -o --out[=FILE]       File to output to
  -h --help-for=CHECKS
  -? --help             Display help message
  -V --version          Print version information
  -v --verbose          Loud verbosity
  -q --quiet            Quiet verbosity

Available checks (See `nix-linter --help-for [CHECK]` for more details):
    DIYInherit
    EmptyInherit
    EmptyLet
    EtaReduce
    FreeLetInFunc
    LetInInheritRecset
    ListLiteralConcat
    NegateAtom
    SequentialLet
    SetLiteralUpdate
    UnfortunateArgName
    UnneededRec
    UnusedArg
    UnusedLetBind
    UpdateEmptySet
    AlphabeticalArgs (disabled by default)
    AlphabeticalBindings (disabled by default)
    BetaReduction (disabled by default)
    EmptyVariadicParamSet (disabled by default)
    UnneededAntiquote (disabled by default)

```
