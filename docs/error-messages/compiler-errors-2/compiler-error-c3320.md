---
title: "コンパイラ エラー C3320 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C3320"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3320"
ms.assetid: 2ef72d9a-1f1d-4b2e-b244-9fd3f3e70cb6
caps.latest.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 9
---
# コンパイラ エラー C3320
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'type': 型には、モジュール 'name' プロパティと同じ名前を指定することはできません  
  
 エクスポートされたユーザー定義型 \(UDT\) は、構造体、クラス、列挙体、共用体、または [\_\_value](../../misc/value.md) の可能性があり、[module](../../windows/module-cpp.md) 属性の name プロパティに渡されたパラメーターと同じ名前を指定することはできません。  
  
 次の例では C3320 が生成されます。  
  
```  
// C3320.cpp #include "unknwn.h" [module(name="xx")]; [export] struct xx {   // C3320 // Try the following line instead // [export] struct yy { int i; };  
```