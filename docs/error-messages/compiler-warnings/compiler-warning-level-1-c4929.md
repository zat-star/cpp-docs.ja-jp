---
title: "コンパイラの警告 (レベル 1) C4929 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4929"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4929"
ms.assetid: 95f8ab4f-4468-4caa-acd5-8f4592f03b3c
caps.latest.revision: 17
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 17
---
# コンパイラの警告 (レベル 1) C4929
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'file' : typelibary は共用体を含みます。'embedded\_idl' 修飾子を無視します。  
  
 [\#import](../Topic/%23import%20Directive%20\(C++\).md) の embedded\_idl 属性はタイプ ライブラリに適用できません。これは、タイプ ライブラリに共用体が存在するためです。  この警告を解決するには、embedded\_idl を使用しないでください。  
  
## 使用例  
 コンポーネントを定義する例を次に示します。  
  
```  
// C4929a.cpp  
// compile with: /LD /link /TLBOUT:C4929a.tlb  
#include <objbase.h>  
[module(name="Test")];  
[public, switch_type(short)] typedef union _TD_UNION_TYPE   {  
   [case(24)]  
      float fM;  
   [case(25)]  
      double dMN;  
   [default]  
      int x;  
} TD_UNION_TYPE;  
  
[export, public] typedef struct _TDW_TYPE {  
   [switch_is(sU)] TD_UNION_TYPE w;  
      short sU;  
} TD_TYPE;  
  
[object, uuid("00000000-0000-0000-0000-000000000001")]  
__interface I {  
   HRESULT f(TD_TYPE*);  
};  
  
[coclass, uuid("00000000-0000-0000-0000-000000000002")]  
struct C : I {  
   HRESULT f(TD_TYPE*) { return 0; }  
};  
```  
  
## 使用例  
 次の例では C4929 エラーが生成されます。  
  
```  
// C4929b.cpp  
// compile with: /c /W1  
#import "C4929a.tlb" embedded_idl   // C4929  
```