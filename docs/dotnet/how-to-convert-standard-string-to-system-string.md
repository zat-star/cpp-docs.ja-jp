---
title: "方法: system::string を標準文字列に変換 |Microsoft ドキュメント"
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
- C++ Standard Library, converting strings to System::String
- string conversion [C++], C++ Standard Library string
- strings [C++], converting
ms.assetid: 1fde79a0-9d0b-44e5-981b-e8f2676c199d
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: c6a2bc4fb1a73954e182ea192047a7ec6ca20c1d
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="how-to-convert-standard-string-to-systemstring"></a>方法: 標準文字列を System::String に変換する
このトピックの内容表示は、C++ 標準ライブラリの文字列を変換する方法 ([\<文字列 >](../standard-library/string.md)) に、<xref:System.String>です。  
  
## <a name="example"></a>例  
  
```  
// convert_standard_string_to_system_string.cpp  
// compile with: /clr  
#include <string>  
#include <iostream>  
using namespace System;  
using namespace std;  
  
int main() {  
   string str = "test";  
   cout << str << endl;  
   String^ str2 = gcnew String(str.c_str());  
   Console::WriteLine(str2);  
  
   // alternatively  
   String^ str3 = gcnew String(str.c_str());  
   Console::WriteLine(str3);  
}  
```  
  
```Output  
test  
test  
test  
```  
  
## <a name="see-also"></a>参照  
 [C++ Interop (暗黙の PInvoke) の使用](../dotnet/using-cpp-interop-implicit-pinvoke.md)