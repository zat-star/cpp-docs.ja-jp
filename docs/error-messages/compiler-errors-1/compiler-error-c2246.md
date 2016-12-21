---
title: "コンパイラ エラー C2246 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C2246"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2246"
ms.assetid: 4f3e4f83-21f3-4256-af96-43e0bb060311
caps.latest.revision: 9
caps.handback.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# コンパイラ エラー C2246
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'identifier': ローカルに定義されたクラスの静的データ メンバーが正しくありません  
  
 ローカル スコープのクラス、構造体、共用体のメンバーが `static` で宣言されています。  
  
 次の例では C2246 が生成されます。  
  
```  
// C2246.cpp // compile with: /c void func( void ) { class A { static int i; };   // C2246  i is local to func static int j;   // OK };  
```