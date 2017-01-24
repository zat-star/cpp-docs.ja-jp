---
title: "コンパイラ エラー C3283 | Microsoft Docs"
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
  - "C3283"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3283"
ms.assetid: c51d912c-cde3-4928-904e-26734c8954ce
caps.latest.revision: 6
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# コンパイラ エラー C3283
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'type': インターフェイスにインスタンス コンストラクターを含めることはできません  
  
 CLR [インターフェイス](../../windows/interface-class-cpp-component-extensions.md)にインスタンス コンストラクターを含めることはできません。  静的コンストラクターが許可されます。  
  
 次の例では C3283 が生成されます。  
  
```  
// C3283.cpp // compile with: /clr interface class I { I();   // C3283 };  
```  
  
 考えられる解決策:  
  
```  
// C3283b.cpp // compile with: /clr /c interface class I { static I(){} };  
```