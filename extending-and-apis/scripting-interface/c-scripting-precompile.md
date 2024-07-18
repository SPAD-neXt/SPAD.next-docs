---
description: Using precompiled Scripting Assemblies
---

# C# Scripting: PreCompile

The internal on-demand scripting interface is limited to several OS-Interactions for security reasons.

You can provide a precompiled C#-Script which has no restrictions, e.g. if you need to access System.Net.

Prequsites:

* .Net Framework 4.8 Assembly
* SPAD.Interfaces.dll must be referenced (Copy to local = false!)
* If the Version-Number of SPAD.Interfaces changes, the assembly must be recompiled

Installation

* Create a directory "Addons" in Documents/SPAD.neXt
* Copy the assembly dll and all it's (non-system) depencies to that directory
* The assembly will be loaded when SPAD.neXt starts, **before** any devices are initialized
*
