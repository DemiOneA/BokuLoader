# Cobalt Strike User-Defined Reflective Loader
Cobalt Strike User-Defined Reflective Loader written in Assembly & C for advanced evasion capabilities.

## Info
+ This is based on Stephan Fewers incredible Reflective Loader project: 
  + https://github.com/stephenfewer/ReflectiveDLLInjection
+ I created this while working through Renz0h's Reflective DLL videos from the Sektor7 Malware Developer Intermediate (MDI) Course.  

## Initial Project Goals
+ Learn how reflective loader works.
+ Write my own reflective loader in assembly.
+ Compatible with Cobalt Strike.
+ Cross compile from macOS/Linux.
+ Figure out how to implement inline assembly into a C project.

## Future Project Goals
+ Use the initial project as a template for more advanced evasion techniques leveraging the flexibility of Assembly.
+ Implement Cobalt Strike options such as no RWX, stompPE, module stomping, changing the MZ header, etc.
+ Write a decent Aggressor script.
+ Support x86.
+ Have different versions of reflective loader to choose from.
+ Implement HellsGate/HalosGate for the initial calls that reflective loader uses (pNtFlushInstructionCache, VirtualAlloc, GetProcAddress, LoadLibraryA, etc).
+ Optimize the assembly code.
+ Some kind of template language overlay that can modify/randomize the registers/methods.

## How to Use
1. Start your Cobalt Strike Team Server without a profile
2. Go to your Cobalt Strike GUI and import the rdll_loader.cna Agressor script
3. Generate your x64 payload (Attacks -> Packages -> Windows Executable (S))

## How to Build (Only tested from macOS at the moment)
1. Install mingw/gcc
2. Run the compile-x64.sh shell script
3. Follow instructions above (How to Use)

## Credits / References
### Reflective Loader
+ https://github.com/stephenfewer/ReflectiveDLLInjection
+ 100% recommend these videos if you're interested in Reflective DLL:  
  + [Dancing with Import Address Table (IAT) - Sektor 7 MDI Course](https://institute.sektor7.net/courses/rto-maldev-intermediate/463262-pe-madness/1435207-dancing-with-iat)
  + [Walking through Export Address Table - Sektor 7 MDI Course](https://institute.sektor7.net/courses/rto-maldev-intermediate/463262-pe-madness/1435189-walking-through-export-address-table)
  + [Reflective Injection Explained - Sektor 7 MDI Course](https://institute.sektor7.net/courses/rto-maldev-intermediate/463258-reflective-dlls/1435355-reflective-injection-explained)
  + [ReflectiveLoader source review - Sektor 7 MDI Course](https://institute.sektor7.net/courses/rto-maldev-intermediate/463258-reflective-dlls/1435383-reflectiveloader-source-review)
### Cobalt Strike User Defined Reflective Loader
+ https://www.cobaltstrike.com/help-user-defined-reflective-loader
### Great Resource for learning Intel ASM
+ [Pentester Academy - SLAE64](https://www.pentesteracademy.com/course?id=7)
### Implementing ASM in C Code with GCC
+ https://outflank.nl/blog/2020/12/26/direct-syscalls-in-beacon-object-files/
+ https://www.cs.uaf.edu/2011/fall/cs301/lecture/10_12_asm_c.html
+ http://gcc.gnu.org/onlinedocs/gcc-4.0.2/gcc/Extended-Asm.html#Extended-Asm
