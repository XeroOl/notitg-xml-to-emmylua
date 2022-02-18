# NotITG XML To EmmyLua converter

This code takes a `.xml` file for OpenITG/NotITG and converts it into a `.lua` file with EmmyLua annotations that should enable language servers to offer intellisense completions.

It can detect names and types from actors. Here are some examples of things it can detect:
```xml

<!-- Name is "prefix_frame" and Type is "ActorFrame" -->
<ActorFrame InitCommand = "%function(self) prefix_frame = self end" />

<!-- Name is "test" and Type is "Actor" -->
<Layer Var = "test" />

<!-- Name is "Proxy[1]" and Type is "ActorProxy"
     the lua table `Proxy = {}` is also generated -->
<Layer Type = "ActorProxy" Name="Proxy[1]"/>
```

## Dependencies / Installation:
A lua interpreter is required. Download and run converter.lua

## Usage:
```
lua converter.lua {{input}} {{output}}
```

