---
title: "Compiler Error C3278 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C3278"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3278"
ms.assetid: 56f818f5-85a6-4792-843b-54fe16327658
caps.latest.revision: 9
caps.handback.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Compiler Error C3278
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

インターフェイス メソッドまたはピュア メソッド 'method' の直接の呼び出しはランタイムに失敗します  
  
 インターフェイス メソッドまたはピュア メソッドが呼び出されましたが、このような呼び出しは許可されていません。  
  
 次の例では C3278 が生成されます。  
  
```  
// C3278_2.cpp  
// compile with: /clr  
using namespace System;  
interface class I  
{  
   void vmf();  
};  
  
public ref class C: public I  
{  
public:  
   void vmf()  
   {  
      Console::WriteLine( "In C::vmf()" );  
      I::vmf(); // C3278  
   }  
  
};  
  
int main()  
{  
   C^ pC = gcnew C;  
   pC->vmf();  
}  
```