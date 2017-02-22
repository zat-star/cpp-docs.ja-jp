---
title: "方法: out パラメーターを指定する | Microsoft Docs"
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
  - "関数パラメーター"
  - "out パラメーター"
ms.assetid: 02862448-603c-4e9d-a5c5-b45fe38446e3
caps.latest.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 9
---
# 方法: out パラメーターを指定する
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

この例では、関数パラメーターが out パラメーターであることを指定する方法、および C\# プログラムからその関数を呼び出す方法を示します。  
  
 out パラメーターは、Visual C\+\+ 内で <xref:System.Runtime.InteropServices.OutAttribute> を使用して指定されます。  
  
## 使用例  
 この例の最初の部分は、out パラメーターを使用する関数を含む型を持つ Visual C\+\+DLL です。  
  
```  
// cpp_out_param.cpp  
// compile with: /LD /clr:safe  
using namespace System;  
public value struct TestStruct {  
   static void Test([Runtime::InteropServices::Out] String^ %s) {  
      s = "a string";  
   }  
};  
```  
  
## 使用例  
 これは、前の例で作成された Visual C\+\+ コンポーネントを利用する C\# クライアントです。  
  
```  
// cpp_out_param_2.cs  
// compile with: /reference:cpp_out_param.dll  
using System;  
class TestClass {  
   public static void Main() {  
      String t;  
      TestStruct.Test(out t);  
      System.Console.WriteLine(t);  
   }  
}  
```  
  
  **a string**   
## 参照  
 [C\+\+ Interop \(暗黙の PInvoke\) の使用](../dotnet/using-cpp-interop-implicit-pinvoke.md)