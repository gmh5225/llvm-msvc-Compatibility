# 1.clang/lib/sema/SemaExpr.cpp 

Problem:
```C++
if (StrStr(windows_name_, pInfo->windows_name_) > 0)
```

[Patch](https://github.com/gmh5225/LLVM_MSVC_Compatibility/blob/main/0001-MSVC-Compatibility.patch)



# 2.clang/include/clang/Lex/Preprocessor.h clang/lib/Lex/PPMacroExpansion.cpp

Problem:
```C++
printf(__FUNCTION__ "Hello, world!\n");
```
[Patch](https://github.com/gmh5225/LLVM_MSVC_Compatibility/blob/main/0002-MSVC-Compatibility.patch)

  
