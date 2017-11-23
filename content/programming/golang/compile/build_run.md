---
title: "Build & Run"
draft: false
---

{{% panel="Running Code" header="Running Code" theme="default" %}}
Using the go run command go can function as a scripting langauge for quick and dirty tasks.
```
# To run a go file simply use the run command
go run main.go
```
{{% /panel %}}

{{% panel="Compiled Executable" header="Compiled Executable" theme="default" %}}
Using the go build command will create an executable file the same name as your go file.
```bash
# To generate a executable file use the go build.
go build scanner.go
# This will create a file called scanner
```
```bash
# Check executable with file
file scanner

# Check file size
ls -l scanner
```
{{% /panel %}}
