# 3-Series Processors and Application Managers #

Each application slot on a proc has a specific application manager. Which one is used depends on the kind of source code you've compiled into the application.

*It becomes helpful when reading error logs to know what is loaded into each program slot.*
 
1. SIMPL Windows Only - This is compiled to a ".bin" file. The .bin file is not a binary module loaded by the operating system as a DLL is. The .bin file is read and interpreted by LogicEngine.exe. LogicEngine.exe is part of the O/S firmware and not included in the program slot.
2. SIMPL Windows and SIMPL+ - The SMW code is compiled to a ".bin" file, and the SIMPL+ code (the USP and USH files of your project) are translated to C#/S# and then compiled to DLL's. The application manager Splusmanagerapp.exe loads and manages the DLL function calls and LogicEngine.exe interprets the .bin file. Application context switching occurs when the SMW code calls S+ functions.
3. SIMPL Windows and SIMPL+ that calls into S# - The SMW code is compiled to a ".bin" file, and the SIMPL+ code (the USP and USH files of your project) are translated into C#/S# and then compiled to DLL's. The S# is compiled into a ".clz". The application manager Splusmanagerapp.exe loads and manages the DLL function calls and LogicEngine.exe interprets the .bin file. Application context switching occurs when the SMW code calls SIMPL+ functions. I believe a  SimplSharpPro.exe process is started (this would seem to be a copy of the EXE included with the firmware) which the S# interface DLL calls into.
4. C# with use of S# Pro libraries - Your application code is compiled into DLL's and the application manager is SimplSharpPro.exe. The DLL is loaded into the application's process space and entry points are called to initialize, run, pause and shut down the control system. 

