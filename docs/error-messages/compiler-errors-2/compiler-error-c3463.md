---
title: "コンパイラ エラー C3463 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C3463"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3463"
ms.assetid: 153efcc0-085c-4615-84ea-d22942618bdf
caps.latest.revision: 3
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 3
---
# コンパイラ エラー C3463
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'type':型は属性 'implements' で使用できません  
  
 [implements](../Topic/implements%20\(C++\).md) 属性に正しくない型が渡されました。 たとえば、`implements` にインターフェイスを渡すことはできますが、インターフェイスへのポインターを渡すことはできません。  
  
## 使用例  
 次の例では C3463 が生成されます。  
  
```  
// C3463.cpp // compile with: /c #include <windows.h> [object, uuid("00000000-0000-0000-0000-000000000001")] __interface X {}; typedef X* PX; [ coclass, uuid("00000000-0000-0000-0000-000000000002"), implements(interfaces=PX) ]   // C3463 // try the following line instead // [ coclass, uuid("00000000-0000-0000-0000-000000000002"), implements(interfaces=X) ] class CMyClass : public X {};  
```