# dotNET_Obfuscation

# .NET Reactor Protection Script

## Introduction

This script is used to protect .NET assemblies using **.NET Reactor**. It applies multiple layers of obfuscation and encryption to prevent reverse engineering, debugging, and tampering.

## Usage

To execute the script, simply run the batch file:

```cmd
cd /d "C:\Program Files (x86)\Eziriz\.NET Reactor"

dotNET_reactor.exe -file "Path\To\Api.dll" -antitamp 1 -control_flow_obfuscation 1 -flow_level 9 -necrobit 1 -resourceencryption 1 -stringencryption 1 -obfuscation 1 -incremental_obfuscation 1 -resourcecompression 1 

timeout /t 3 /nobreak

copy /Y "Path\To\API_Secure\Api.dll" "Path\To\Api.dll"

rmdir /s /q "Path\To\API_Secure"
```

Make sure to replace `Path\To\Api.dll` and `Path\To\API_Secure` with the actual paths where your DLL is located and where you want the protected version to be stored.

## Explanation of Parameters

The following options are used in the script to maximize the security of the assembly:

### **1. Anti-Tamper Protection**

```cmd
-antitamp 1
```

Prevents the protected assembly from being modified or tampered with by hacker tools.

### **2. Control Flow Obfuscation**

```cmd
-control_flow_obfuscation 1
```

Scrambles the control flow of methods, making it difficult for humans and decompilers to understand the logic.

### **3. Control Flow Strength Level**

```cmd
-flow_level 9
```

Defines the intensity of the control flow obfuscation. Level **9** provides the strongest obfuscation.

### **4. NecroBit Protection**

```cmd
-necrobit 1
```

A special security mechanism that works for both applications and libraries, adding an extra layer of protection.

### **5. Mapping File Generation**

```cmd
-mapping_file 1
```

Creates a mapping file that correlates obfuscated names with original names. Useful for debugging obfuscated stack traces.

### **6. Name Obfuscation**

```cmd
-obfuscation 1
```

Obfuscates all non-public class and member names to prevent easy decompilation.

### **7. Incremental Obfuscation**

```cmd
-incremental_obfuscation 1
```

Ensures that the same obfuscated names are generated for each build, preventing unnecessary changes across versions.

### **8. Resource Encryption**

```cmd
-resourceencryption 1
```

Encrypts embedded resources to prevent unauthorized access.

### **9. Resource Compression**

```cmd
-resourcecompression max
```

Compresses embedded resources for better protection. The `max` option provides the highest security level.

### **10. String Encryption**

```cmd
-stringencryption 1
```

Encrypts string literals to prevent easy extraction of sensitive data from the assembly.

## Script Workflow

1. Navigates to the **.NET Reactor** installation directory.
2. Runs the **.NET Reactor** command-line tool with the specified protection options.
3. Waits a few seconds to ensure the process is completed.
4. Copies the newly protected DLL from the `API_Secure` folder to the original destination.
5. Deletes the temporary `API_Secure` folder.
6. Displays a message confirming successful protection.

## Notes

- Ensure that **.NET Reactor** is installed and properly configured.
- Run the script as an **Administrator** for full permissions.
- Adjust the paths accordingly to match your project structure.

### **Conclusion**

This script automates the protection of .NET assemblies using **.NET Reactor**, making it harder for attackers to decompile, modify, or reverse-engineer your application. 🚀

