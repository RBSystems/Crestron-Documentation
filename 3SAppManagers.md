# 3-Series Procs and Application Managers #

Each application slot on a proc has a specific application manager. Which one is used depends on the kind of source code you've compiled into the application.

*It becomes helpful when reading error logs to know what is loaded into each program slot.*
 
1. SIMPL Windows Only - This is compiled to a ".bin" file. The .bin file is not a binary module loaded by the operating system as a DLL is. The .bin file is read and interpreted by LogicEngine.exe. LogicEngine.exe is part of the O/S firmware and not included in the program slot.
2. SIMPL Windows and SIMPL+ - The SMW code is compiled to a ".bin" file, and the S+ code is compiled to DLL's that correspond to the USP and USH files of your project. The application manager Splusmanager.exe loads and manages the DLL function calls and LogicEngine.exe interprets the .bin file. Application context switching occurs when the SMW code calls S+ functions.
3. SIMPL Windows and SIMPL+ that calls into S# - The SMW code is compiled to a ".bin" file, and the S+ code is compiled to DLL's that correspond to the USP and USH files of your project. The S# is compiled into a ".clz". A S# interface DLL is part of the Splusmanager application. The application manager Splusmanager.exe loads and manages the DLL function calls and LogicEngine.exe interprets the .bin file. Application context switching occurs when the SMW code calls S+ functions, and S# functions may also be called. I believe a  SimplSharpPro.exe process is started (this would seem to be a copy of the EXE included with the firmware) which the S# interface DLL calls into.
4. C# (w/S# and/or S# Pro libraries). Your application code is compiled into DLL's and the application manager is SimplSharpPro.exe. The DLL is loaded into the application's process space and entry points are called to initialize, run, pause and shut down the control system. 


