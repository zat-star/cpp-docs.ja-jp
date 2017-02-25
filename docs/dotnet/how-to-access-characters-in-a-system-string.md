---
title: "方法: System::String の文字にアクセスする | Microsoft Docs"
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
  - "文字 [C++], アクセス (System::String 内の)"
  - "例 [C++], 文字列"
  - "文字列 [C++], アクセス (文字に)"
ms.assetid: cfc89756-aef3-4988-907e-fb236dcb7087
caps.latest.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 9
---
# 方法: System::String の文字にアクセスする
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

<xref:System.String> オブジェクトの文字にアクセスすると、`wchar_t*` 文字列を受け取るアンマネージ関数を効率よく呼び出すことができます。  このメソッドは、<xref:System.String> オブジェクトの 1 文字目への内部ポインターを生成します。  このポインターを直接操作するか、固定して、通常の `wchar_t` 文字列を使用する関数に渡すことができます。  
  
## 使用例  
 `PtrToStringChars` は <xref:System.Char> を返します。これは、`byref` とも呼ばれる内部ポインターです。  このため、ガベージ コレクションの対象になります。  ネイティブ関数に渡さない限り、このポインターを固定する必要はありません。  
  
 次のコードがあるとします。`ppchar` は内部ポインターであるため、固定する必要はありません。ガベージ コレクターが指している文字列を移動した場合は、`ppchar` も更新されます。  [pin\_ptr \(C\+\+\/CLI\)](../Topic/pin_ptr%20\(C++-CLI\).md) を使用しない場合は、固定が原因でパフォーマンスが低下することなくコードを実行できます。  
  
 `ppchar` をネイティブ関数に渡す場合は、固定ポインターを使用する必要があります。ガベージ コレクターは、アンマネージ スタック フレーム上のポインターを更新できません。  
  
```  
// PtrToStringChars.cpp  
// compile with: /clr  
#include<vcclr.h>  
using namespace System;  
  
int main() {  
   String ^ mystring = "abcdefg";  
  
   interior_ptr<const Char> ppchar = PtrToStringChars( mystring );  
  
   for ( ; *ppchar != L'\0'; ++ppchar )  
      Console::Write(*ppchar);  
}  
```  
  
  **abcdefg**   
## 使用例  
 固定を必要とする例を次に示します。  
  
```  
// PtrToStringChars_2.cpp  
// compile with: /clr  
#include <string.h>  
#include <vcclr.h>  
// using namespace System;  
  
size_t getlen(System::String ^ s) {  
   // Since this is an outside string, we want to be secure.  
   // To be secure, we need a maximum size.  
   size_t maxsize = 256;  
   // make sure it doesn't move during the unmanaged call  
   pin_ptr<const wchar_t> pinchars = PtrToStringChars(s);  
   return wcsnlen(pinchars, maxsize);  
};  
  
int main() {  
   System::Console::WriteLine(getlen("testing"));  
}  
```  
  
 **7**   
## 使用例  
 内部ポインターには、ネイティブ C\+\+ ポインターのすべてのプロパティがあります。  たとえば、このポインターを使用すると、リンクされたデータ構造体を調べ、唯一のポインターで挿入と削除ができます。  
  
```  
// PtrToStringChars_3.cpp  
// compile with: /clr /LD  
using namespace System;  
ref struct ListNode {  
   Int32 elem;   
   ListNode ^ Next;  
};  
  
void deleteNode( ListNode ^ list, Int32 e ) {   
   interior_ptr<ListNode ^> ptrToNext = &list;  
   while (*ptrToNext != nullptr) {  
      if ( (*ptrToNext) -> elem == e )  
         *ptrToNext = (*ptrToNext) -> Next;   // delete node  
      else  
         ptrToNext = &(*ptrToNext) -> Next;   // move to next node  
   }  
}  
```  
  
## 参照  
 [C\+\+ Interop \(暗黙の PInvoke\) の使用](../dotnet/using-cpp-interop-implicit-pinvoke.md)