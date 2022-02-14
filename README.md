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

  
  
# 3.lld/COFF/Writer.cpp

Problem:
```C++
Fix the characteristics of some sections like ".voltbl". Or the program will be crash sometimes.
```

[Patch](https://github.com/gmh5225/LLVM_MSVC_Compatibility/blob/main/0003-MSVC-Compatibility.patch)



# 4.clang/lib/AST/ASTContext.cpp

Problem:
```C++
void OutputTrace(int place_holder, ...)
{
	va_list args;
	va_start(args, place_holder);
	bool unicode = va_arg(args, bool);
}
```

[Patch](https://github.com/gmh5225/LLVM_MSVC_Compatibility/blob/main/0004-MSVC-Compatibility.patch)



# 5.lld/COFF/Driver.cpp

Problem:
```C++
1>lld-link : error : could not open '/RELEASE': no such file or directory
1>lld-link : error : could not open '/kernel': no such file or directory
1>lld-link : error : could not open '/pdbcompress': no such file or directory
```

[Patch](https://github.com/gmh5225/LLVM_MSVC_Compatibility/blob/main/0005-MSVC-Compatibility.patch)



# 6.lld/COFF/SymbolTable.cpp

Problem:
```C++
1>lld-link : error : duplicate symbol: g_GlobalNotifyRecord
1>>>> defined at x64\Debug\Broadcast.obj
1>>>> defined at x64\Debug\Vpid.obj
```

[Patch](https://github.com/gmh5225/LLVM_MSVC_Compatibility/blob/main/0006-MSVC-Compatibility.patch)



# 7.clang/include/clang/Driver/Options.td

Problem:
```C++
Null ptr is invalid.
```

[Patch](https://github.com/gmh5225/LLVM_MSVC_Compatibility/blob/main/0007-MSVC-Compatibility.patch)



# 8.lld/COFF/Writer.cpp

Problem:
```C++
Unused IMAGE_DLL_CHARACTERISTICS_TERMINAL_SERVER_AWARE
```

[Patch](https://github.com/gmh5225/LLVM_MSVC_Compatibility/blob/main/0008-MSVC-Compatibility.patch)



# 9.llvm/lib/Transforms/Scalar/LoopIdiomRecognize.cpp

Problem:
```C++
#define ZERO_MEMORY(addr,size) while (size-->0)\
								{\
									*addr++ = 0;\
								}\
->>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>
will be optimized to 'memset'.
```

[Patch](https://github.com/gmh5225/LLVM_MSVC_Compatibility/blob/main/0009-MSVC-Compatibility.patch)



# 10.clang/lib/Parse/ParseDecl.cpp clang/lib/Parse/ParseDecl.cpp

Problem:
```C++
template <typename R, typename... Args>
struct MyTestTemplate;

template <typename R, typename... Args>
struct MyTestTemplate<R(__stdcall)(Args...)>
{
};
->>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>
error : function cannot return function type 'R (Args...)'
```

[Patch](https://github.com/gmh5225/LLVM_MSVC_Compatibility/blob/main/0010-MSVC-Compatibility.patch)



# 11.clang/tools/driver/driver.cpp

Problem:
```C++
 __m128i x1, x2;
 __m128i x3 = _mm_shuffle_epi8(x1, x2);
 ->>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>
 _mm_shuffle_epi8 needs '-mssse3'
```

[Patch](https://github.com/gmh5225/LLVM_MSVC_Compatibility/blob/main/0011-MSVC-Compatibility.patch)



# 12.lld/COFF/Driver.cpp

Problem:
```C++
#pragma comment(linker, "/ALIGN:0x10000")
->>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>
Error:/ALIGN: is not allowed in .drectve
```

[Patch](https://github.com/gmh5225/LLVM_MSVC_Compatibility/blob/main/0012-MSVC-Compatibility.patch)
