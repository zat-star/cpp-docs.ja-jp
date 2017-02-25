---
title: "コンパイラ エラー C3455 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C3455"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3455"
ms.assetid: 218e5cfe-5391-4eeb-81c2-85c47e3a6cd2
caps.latest.revision: 5
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 5
---
# コンパイラ エラー C3455
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'attribute': どの属性コンストラクターも引数に一致しませんでした  
  
 無効な値が属性の宣言に使用されました。  詳細については、「[attribute](../../windows/attribute.md)」を参照してください。  
  
## 使用例  
 次の例では C3455 が生成されます。  
  
```  
// C3455.cpp // compile with: /clr /c using namespace System; [attribute("MyAt")]   // C3455 // try the following line instead // [attribute(All)] ref struct MyAttr { MyAttr() {} };  
```