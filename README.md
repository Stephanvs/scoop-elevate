# elevate

If you use batch files to automate tasks on a computer running Windows 11, 10, 8, or 7, you have probably encountered situations when you needed to start a program elevated (a.k.a. as administrator). For example, if you want to share a folder automatically from a batch file, you would use the net share command. However, unlike many other programs that ask for the administrator's approval, net share does not do that and simply returns the error code 5 ("access denied") if it was started by a standard user. How to force that program to start elevated from a batch file? That's the purpose of the Elevate utility that we've created to solve such a problem.

## Install

```bash
scoop bucket add scoop-elevate https://github.com/stephanvs/scoop-elevate.git
scoop install elevate
```

## Usage

```pwsh
$ elevate -?
Elevate v.1.1 (32-bit) - Starts a process elevated ("As Admininstrator").

Copyright (c) 2010, WinAbility Software Corp. All rights reserved.
Visit http://www.winability.com/elevate for more information and updates.

Usage:

  elevate [-opt1] [-opt2...] [path\]file[.exe] [param1 [param2...]]

Where -optN can be one of the following:

  -?         - Display this screen and exit
  -info      - Open the web page with more information and exit
  -wait4idle - Wait for the target process to initialize before returning
  -wait4exit - Wait for the target process to finish before returning
  -noui      - Don't display any messages, even if an error occurs

  file       - The file name of the program to launch elevated
  paramN     - Optional parameters (as expected by the program being launched)

Example:

  elevate -wait4exit -noui "C:\Windows\System32\Notepad.exe" "D:\Test.txt"
```

## Attribution & License
- https://www.winability.com/elevate/
- https://www.winability.com/end-user-license-agreement/?elevate
