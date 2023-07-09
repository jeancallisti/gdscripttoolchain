# gdscripttoolchain
A home for advanced tools involving Godot's GDScript: Syntax analyzers, plugins, etc.

# Current state
This repo is still in the "early research" phase. It does not host any code yet. **If you are a developer proficient with syntactic analysis, please feel free to contibute any project you might like to this repo.**


## What is GDScript?

GDScript is the scripting language used by the Godot game engine. It has a syntax similar to Python. It can use fully-dynamic typing or semi-string typing depending on the settings. Godot 3.x uses GDScript 1. Godot 4.x uses GDscript 2, which allows slightly stricter syntactic capabilities.

## Why a toolchain?

No matter what sort of manipulation you intend on implementing around GDScript, at the moment your only two options are : 
- The native "IDE" (code editor) and compiler/interpreter/debugger embedded directly in the Godot Editor. That code editor is relatively poor in terms of features and ergonomy.
- Some of the third-party code bases out there, which are not consistent with one another (in terms of languages, flows, etc.), and have dubious support (there was a boom circa 2020 and then not much happened)

You can use the abilities of C# (and all its ecosystem) *only* if your project is of the "Godot Mono" kind. If you intend to biuld on top of existing plugins written entirely in GDScript then you are stuck with GDScript.

## Some existing resources

Some resources related to parsing and manipulating the GDScript language, in no particular order:
- **"The new GDScript parser"** : https://docs.ctags.io/en/latest/parser-gdscript.html
- **gd2cs** : An attempt at writing a transpiler from GDScript to C#. It works with individual files. The syntax analysis relies entirely on Regexps. It is written in python. https://github.com/kiriri/gd2cs.py
- **GDScript to Python to C transpiler** : compiles GDScript to C (using Nuitka and zig). As a by product (?) it can transpile "minimal scripts" to Python. https://github.com/LinuxUserGD/gdscript-transpiler-source
- **Godot VSCode plugin** : A plugin for writing GDScript code inside VSCode. It provides syntax highlight and the like. https://github.com/godotengine/godot-vscode-plugin

## Where to start?

It would be useful to start with a syntax parser for GDScript, written in a language univeral enough (ANTLR or the like, which can then generate code in any other language for consumption), maintained on its own (to be always up-to-date) and which could act as a server for other tools.

The **Godot VSCode plugin** (mentionned above) is probably the most widely-adopted code base and it might be efficient to build around it.


