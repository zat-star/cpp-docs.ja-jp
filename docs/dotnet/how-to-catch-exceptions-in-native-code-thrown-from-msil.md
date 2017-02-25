---
title: "方法: MSIL からスローされるネイティブ コードの例外をキャッチする | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "キャッチ (例外の), スロー (MSIL から)"
  - "例外, キャッチ"
  - "MSIL, キャッチ (ネイティブ コードの例外を)"
ms.assetid: c15afd2b-8505-43bf-8a4a-f1d41532a124
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# 方法: MSIL からスローされるネイティブ コードの例外をキャッチする
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

ネイティブ コードでは、MSIL からネイティブ C\+\+ 例外をキャッチできます。`__try` と `__except`の CLR 例外をキャッチできます。  
  
 詳細については、「[構造化例外処理](../cpp/structured-exception-handling-c-cpp.md)」および「[C\+\+ 例外処理](../cpp/cpp-exception-handling.md)」を参照してください。  
  
## 使用例  
 次の例は、2 種類の関数、1 ネイティブ例外をスローする、および MSIL が例外をスローする別のモジュールを定義します。  
  
```  
// catch_MSIL_in_native.cpp  
// compile with: /clr /c  
void Test() {  
   throw ("error");  
}  
  
void Test2() {  
   throw (gcnew System::Exception("error2"));  
}  
```  
  
## 使用例  
 次の例は、ネイティブおよび MSIL が例外をキャッチするモジュールを定義します。  
  
```  
// catch_MSIL_in_native_2.cpp  
// compile with: /clr catch_MSIL_in_native.obj  
#include <iostream>  
using namespace std;  
void Test();  
void Test2();  
  
void Func() {  
   // catch any exception from MSIL  
   // should not catch Visual C++ exceptions like this  
   // runtime may not destroy the object thrown  
   __try {  
      Test2();  
   }  
   __except(1) {  
      cout << "caught an exception" << endl;  
   }  
  
}  
  
int main() {  
   // catch native C++ exception from MSIL  
   try {  
      Test();  
   }  
   catch(char * S) {  
      cout << S << endl;  
   }  
   Func();  
}  
```  
  
  **エラー**  
**例外をつかまえました**   
## 参照  
 [Exception Handling](../windows/exception-handling-cpp-component-extensions.md)