---
title: "方法: system::string を標準文字列に変換します |。Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: get-started-article
dev_langs:
- C++
helpviewer_keywords:
- C++ Standard Library, converting System::String to standard string
- string conversion, System::String
ms.assetid: 79e2537e-d4eb-459f-9506-0e738045b59e
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 6bac914a2803390fa737acce5d424d56079777a9
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="how-to-convert-systemstring-to-standard-string"></a>方法: System::String を標準文字列に変換する
Vcclr.h の <xref:System.String> を使用せずに、`std::string` を `std::wstring` または `PtrToStringChars` に変換できます。  
  
## <a name="example"></a>例  
  
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
  
## <a name="see-also"></a>参照  
 [C++ Interop (暗黙の PInvoke) の使用](../dotnet/using-cpp-interop-implicit-pinvoke.md)