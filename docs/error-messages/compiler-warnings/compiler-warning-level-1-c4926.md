---
title: "コンパイラの警告 (レベル 1) C4926 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C4926"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4926"
ms.assetid: 5717fce0-146f-4ef2-bde0-e9a01c0922d1
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# コンパイラの警告 (レベル 1) C4926
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'identifier': シンボルは既に定義されています。属性は無視されます。  
  
 事前宣言が見つかりましたが、同じ名前の属性付きコンストラクトが既に存在します。 事前宣言の属性は無視されます。  
  
 次の例では C4926 警告が生成されます。  
  
```  
// C4926.cpp // compile with: /W1 [module(name="MyLib")]; [coclass] struct a { }; [coclass] struct a;   // C4926 int main() { }  
```