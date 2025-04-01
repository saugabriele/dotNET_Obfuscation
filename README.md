# dotNET_Obfuscation

# .NET Reactor Protection Script

## Introduction

This script is used to protect .NET assemblies using **.NET Reactor**. It applies multiple layers of obfuscation and encryption to prevent reverse engineering, debugging, and tampering.

## Usage

To execute the script, simply run the batch file:

```cmd
del /f /q "Path\To\App.pdb"

cd /d "C:\Program Files (x86)\Eziriz\.NET Reactor"

dotNET_reactor.exe -file "Path\To\App.dll" -antitamp 1 -control_flow_obfuscation 1 -flow_level 9 -necrobit 1 -resourceencryption 1 -stringencryption 1 -obfuscation 1 -incremental_obfuscation 1 -resourcecompression max

timeout /t 10 /nobreak && ^
copy /Y "Path\To\APP_Secure\App.dll" Path\To\App.dll" && ^
rmdir /s /q "Path\To\APP_Secure"

```

Make sure to replace `Path\To\App.dll` and `Path\To\APP_Secure` with the actual paths where your DLL is located and where you want the protected version to be stored.

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
4. Copies the newly protected DLL from the `APP_Secure` folder to the original destination.
5. Deletes the temporary `APP_Secure` folder.
6. Displays a message confirming successful protection.

## Notes

- Ensure that **.NET Reactor** is installed and properly configured.
- Run the script as an **Administrator** for full permissions.
- Adjust the paths accordingly to match your project structure.

### **Conclusion**

This script automates the protection of .NET assemblies using **.NET Reactor**, making it harder for attackers to decompile, modify, or reverse-engineer your application. 🚀


# Eazfuscator.NET Code Obfuscation

## Overview
Eazfuscator.NET is a powerful obfuscation tool designed to protect .NET applications from reverse engineering. This README provides instructions on how to use Eazfuscator.NET to obfuscate your code and details the various security features it applies.

## Installation
Ensure that Eazfuscator.NET is installed on your system before proceeding. You can download it from the official website.

## Usage Instructions

### Step 1: Execute the Obfuscation Command
Run the following command to obfuscate your application's DLL:

```sh
# Obfuscate the main application project DLL
eazfuscator.net --msbuild-project-path "Path\To\App\Project.csproj" --protect-project

# Obfuscate the Business Logic Layer (BLL) DLL
eazfuscator.net --msbuild-project-path "Path\To\App\BLL.csproj" --protect-project

# Obfuscate the Data Access Layer (DAL) DLL
eazfuscator.net --msbuild-project-path "Path\To\App\DAL.csproj" --protect-project

# Obfuscate the Database Access (DBA) DLL
eazfuscator.net --msbuild-project-path "Path\To\App\DBA.csproj" --protect-project

# Obfuscate the Data Transfer Object (DTO) DLL
eazfuscator.net --msbuild-project-path "Path\To\App\DTO.csproj" --protect-project
```

### Step 2: Publish the Application
Once the obfuscation is completed, navigate to the project directory and publish the application in Release mode using the following command:

```sh
cd Path/To/Project
dotnet publish -c Release
```

### Step 3: Obfuscated DLLs in Release Build
After running the `dotnet publish -c Release` command, the obfuscated DLLs will be available in the `bin\Release\netX.X\publish` folder. These DLLs will have the obfuscation applied, making the code harder to reverse-engineer. The main project DLL, along with other project DLLs (such as BLL, DAL, DBA, DTO), will also be obfuscated.


## Features and Functionalities

### Symbols Renaming
Renames function names, variables, and classes to meaningless identifiers, making it harder for attackers to understand the structure of the code.

### String Encryption and Compression
Encrypts and compresses strings in your code, preventing sensitive information from being exposed while also reducing assembly size.

### Code and Data Virtualization
Converts .NET bytecode into an unrecognizable sequence of byte instructions. Each obfuscation creates a new virtual machine, adding an additional layer of protection.

### Homomorphic Encryption
Applies homomorphic encryption to secure critical parts of the code, making them completely intangible to attackers.

### Automatic Code Optimization
Improves code performance automatically without requiring manual intervention.

### Resource Encryption and Compression
Protects sensitive resources, such as images and sound files, by encrypting and compressing them.

### Code Control Flow Obfuscation
Modifies the program’s control flow, making decompilers struggle to reverse-engineer the logic of the code.

### Assemblies Merging and Embedding
Merges multiple assemblies into a single one, reducing the risk of attackers extracting individual components.

### XML Documentation Filter
Automatically removes implementation details from XML documentation files to prevent information leaks.

### Debugging Support
Maintains debugging capabilities by allowing stack trace readability, exception tracking, and debugger attachment.

## Conclusion
Eazfuscator.NET provides comprehensive protection for your .NET applications by obfuscating code, securing resources, and enhancing performance. Follow the steps above to secure your software against reverse engineering.
