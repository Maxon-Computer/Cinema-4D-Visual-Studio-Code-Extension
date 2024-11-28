# Cinema 4D Connector - Visual Studio Code Extension

Provides an extension for VS Code to exchange code between the Script Manager of Cinema 4D and VS Code.

The extension also provides syntax highlighting for resource files and string resources as used by Cinema 4D, as well as other tools to assist Cinema 4D plugins and scripts developers.

All the commands of this extension can be found by pressing `ctrl+shift+P` and searching for `C4D`.

![Cinema 4D Python Debugging in Visual Studio Code](/image/vscode_example.png)

## Installation

To use all the features it is necessary to install:

- From Cinema 4D 2023.2 you do not need to install any Cinema 4D Plugins. Activate the connection by opening `Extension > Script Manager`, then `Edit > Start/Stop Code Exchanger`. For more information please read the [Cinema 4D Connector documentation](https://help.maxon.net/c4d/en-us/#html/5896.html#codeexchangesendtoIDE).

![Cinema 4D Code Exchanger](https://github.com/user-attachments/assets/238a6dce-265c-4522-a02e-7f38a90388d0)

- From Cinema 4D S26+ to Cinema 2023.1 you need the Cinema 4D plugin, downloadable [here](https://github.com/Maxon-Computer/Cinema-4D-Visual-Studio-Code-Extension/releases). Once downloaded, extract the archive to the Cinema 4D S26+ plugins folder. You then need to activate the extension in the Cinema 4D preferences in the `Extensions | Code Exchange` menu, activate the WebSocket Json checkbox.

- The `Cinema 4D Connector` extension for Visual Studio code, directly accessible in the Visual Studio code marketplace, or download it [here](https://github.com/Maxon-Computer/Cinema-4D-Visual-Studio-Code-Extension/releases).

## Features

In-depth documentation can be found in [Cinema 4D Connector - Documentation](https://help.maxon.net/c4d/en-us/#html/5896.html#codeexchangesendtoIDE).

* **Load Script in Script Manager**: Load the active script from Visual Studio Code editor to Cinema 4D script manager. 
* **Execute in Cinema 4D as a Script in Script Manager**: Execute a script directly into Cinema 4D.
* **Debug in Cinema 4D as a Script in Script Manager**: Start a debugging session for the given script to Cinema 4D.
* **Autocompletion for the `c4d` Python package**: Provide autocompletion on the fly when typing for the c4d package.
* **Load Cinema 4D Script Template**: Loads a template script.
* **Python Console output forwarding**: Cinema 4D Python console outputs is forwarded to a Visual Studio Code console called "Cinema 4D".
* **Syntax highlighting for \*.res and \*.str files**: The syntax for files with the extension .str and .res has a syntax coloring.

## Known Issues

- Autocompletion does not work for the `maxon` package.
- Autocompletion does not work for temporary scripts from Cinema 4D, those whose path begins with `Root@`, e.g. `Root@12345678/Scripts@12345678/untitled.py.`
- Autocompletion for methods from the `c4d` package will generate incomplete default argument if this argument is part of the `c4d` package, e.g. the autocompletion will output only `BaseContainer` while it should be `c4d.BaseContainer`.
- When the `Load Script in Script Manager` command is used on an untitled file, it creates a new temporary file in Cinema 4D and this is returned to Visual Studio Code. This file should be used to exchange data to/from Cinema 4D.
- The first debugging session will show a message about the deprecated use of `ptvsd`, this is a false positive and can be ignored.

## License

This extension is licensed under the [Apache 2.0 License](LICENSE).
