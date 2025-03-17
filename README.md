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


Eazfuscator.NET Code Obfuscation

Overview

This README file explains how to obfuscate your code using Eazfuscator.NET. The obfuscation process is designed to protect your application from reverse engineering by making it harder for attackers to understand or extract sensitive information. The provided commands and the functionalities of Eazfuscator.NET are outlined below.

Commands to Obfuscate Your Code

Step 1: Navigate to Your Application Directory

To begin the obfuscation process, first navigate to the directory of your application using the following command:

cd "Path/To/App"

Replace "Path/To/App" with the actual path to the directory containing your application.

Step 2: Execute the Obfuscation Command

Once you are in the application directory, run the following command to obfuscate your application's DLL:

eazfuscator.net "Path\To\App\App.dll"

Replace "Path\To\App\App.dll" with the actual path to the DLL file you wish to obfuscate. This command will obfuscate the provided DLL and apply several protection techniques to make your code more secure.

Functionalities Performed by Eazfuscator.NET

1. Symbols Renaming

Symbols, such as function names, variables, and class names, are crucial for understanding a program's structure. Eazfuscator.NET renames these symbols to meaningless names, making it difficult for an attacker to understand the functionality of the code. This simple yet effective technique helps protect your intellectual property by obfuscating the meaning of the symbols in the code.

2. String Encryption and Compression

Strings in your code can expose sensitive information about the program's inner workings. Eazfuscator.NET encrypts and compresses these strings during the obfuscation process. At runtime, these encrypted strings are decrypted, ensuring that the information remains protected. Additionally, string compression reduces the size of the assembly, making it more efficient.

3. Code and Data Virtualization

For more sensitive sections of your code, Eazfuscator.NET uses code and data virtualization. This technique transforms your .NET bytecode into a custom, unrecognizable sequence of byte instructions. The transformed code still functions as expected at runtime but appears as a random sequence, making it much more difficult for attackers to reverse-engineer the program. Every time you obfuscate your program, a new custom virtual machine is created, adding another layer of protection.

4. Homomorphic Encryption

Eazfuscator.NET integrates homomorphic encryption in conjunction with virtualization to secure specific parts of your code. Homomorphic encryption allows computations to be performed on encrypted data without decrypting it. This makes the protected circuits of your program completely intangible to attackers, providing a high level of security for sensitive code sections.

5. Automatic Code Optimization

Eazfuscator.NET automatically optimizes your code for better performance. This optimization helps improve the efficiency of your program, eliminating the need for you to manually tweak the code for performance. The obfuscator performs the optimization behind the scenes, allowing you to focus on functionality rather than performance concerns.

6. Resource Encryption and Compression

If your application includes resources such as images, sounds, or other assets, these may contain sensitive information. Eazfuscator.NET allows you to encrypt and compress these resources, protecting them from unauthorized access. This feature is particularly useful if your program contains private keys or proprietary assets that need to be safeguarded.

7. Code Control Flow Obfuscation

To further obfuscate the code, Eazfuscator.NET applies control flow obfuscation. This technique alters the control flow of the program by replacing equivalent instructions with functionally different but syntactically equivalent ones. This makes it more difficult for decompilers to reverse-engineer the original high-level code, significantly increasing the complexity of understanding and attacking the program.

8. Assemblies Merging and Embedding

Eazfuscator.NET can merge or embed multiple assemblies into a single one. This makes it harder for an attacker to extract individual parts of the program. You can specify which assemblies to merge or embed, and the obfuscator takes care of the process during obfuscation, ensuring that everything is seamlessly integrated.

9. XML Documentation Filter

If your application includes XML documentation files that contain sensitive implementation details, Eazfuscator.NET automatically filters out any potentially revealing information from these files. This ensures that no internal details about private types, methods, or fields are exposed through the documentation.

10. Debugging Support

After obfuscation, your assembly does not become a completely non-debuggable mess. Eazfuscator.NET retains the ability to debug obfuscated code. You can still view readable stack traces, get line numbers for unhandled exceptions, and attach a debugger to your obfuscated code for troubleshooting.

Conclusion

By following the above commands and utilizing Eazfuscator.NET’s powerful obfuscation techniques, you can effectively protect your .NET application from reverse engineering and unauthorized access.
