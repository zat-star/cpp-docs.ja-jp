---
title: "方法: System::String を標準文字列に変換する | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "get-started-article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "標準 C++ ライブラリ, 変換 (System::String を標準の文字列に)"
  - "文字列変換, System::String"
ms.assetid: 79e2537e-d4eb-459f-9506-0e738045b59e
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 9
---
# 方法: System::String を標準文字列に変換する
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Vcclr.h の `PtrToStringChars` を使用せずに、<xref:System.String> を `std::string` または `std::wstring` に変換できます。  
  
## 使用例  
  
```  
// convert_system_string.cpp  
// compile with: /clr  
#include <string>  
#include <iostream>  
using namespace std;  
using namespace System;  
  
void MarshalString ( String ^ s, string& os ) {  
   using namespace Runtime::InteropServices;  
   const char* chars =   
      (const char*)(Marshal::StringToHGlobalAnsi(s)).ToPointer();  
   os = chars;  
   Marshal::FreeHGlobal(IntPtr((void*)chars));  
}  
  
void MarshalString ( String ^ s, wstring& os ) {  
   using namespace Runtime::InteropServices;  
   const wchar_t* chars =   
      (const wchar_t*)(Marshal::StringToHGlobalUni(s)).ToPointer();  
   os = chars;  
   Marshal::FreeHGlobal(IntPtr((void*)chars));  
}  
  
int main() {  
   string a = "test";  
   wstring b = L"test2";  
   String ^ c = gcnew String("abcd");  
  
   cout << a << endl;  
   MarshalString(c, a);  
   c = "efgh";  
   MarshalString(c, b);  
   cout << a << endl;  
   wcout << b << endl;  
}  
```  
  
```  
test  
abcd  
efgh  
```  
  
## 参照  
 [C\+\+ Interop \(暗黙の PInvoke\) の使用](../dotnet/using-cpp-interop-implicit-pinvoke.md)