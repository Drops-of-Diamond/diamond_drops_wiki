* Install [VS Code](https://code.visualstudio.com/download)
* Follow [this blog post](https://medium.com/@royalstream/rust-development-using-vs-code-on-os-x-debugging-included-bc10c9863777) to setup debugging with breakpoints using LLDB in VS Code.
* Troubleshoot [by following these steps](https://medium.com/@ltfschoen/im-using-macos-10-12-861c8211006) 
* Example Debug Config file **Diamond-drops/.vscode/launch.json**. Use by going to menu: Debug > Start Debugging. Note that you shouldn't have to build the project first, as running these debuggers will just run `cargo run -mode c` for example.
```
{
  // Use IntelliSense to learn about possible attributes.
  // Hover to view descriptions of existing attributes.
  // For more information, visit: https://go.microsoft.com/fwlink/?linkid=830387
  "version": "0.2.0",
  "configurations": [
    {
      "type": "lldb",
      "request": "launch",
      "name": "Debug - Mode - Collator",
      "program": "${workspaceFolder}/target/debug/diamond_drops",
      "args": "-mode c",
      "cwd": "${workspaceFolder}",
      "terminal": "integrated"
    },
    {
      "type": "lldb",
      "request": "launch",
      "name": "Debug - Mode - Proposer",
      "program": "${workspaceFolder}/target/debug/diamond_drops",
      "args": "-mode p",
      "cwd": "${workspaceFolder}",
      "terminal": "integrated"
    },
    {
      "type": "lldb",
      "request": "launch",
      "name": "Debug - Mode - Both",
      "program": "${workspaceFolder}/target/debug/diamond_drops",
      "args": "-mode b",
      "cwd": "${workspaceFolder}",
      "terminal": "integrated"
    }
  ]
}
```

* Example Build Task file **Diamond-drops/.vscode/tasks.json**. Use by going to menu: Tasks > Run Build Task
```
{
  // See https://go.microsoft.com/fwlink/?LinkId=733558
  // for the documentation about the tasks.json format
  "version": "2.0.0",
  "tasks": [
    {
      "label": "cargo build",
      "type": "shell",
      "command": "cargo build",
      "group": {
        "kind": "build",
        "isDefault": true
      }
    }
  ]
}
```
