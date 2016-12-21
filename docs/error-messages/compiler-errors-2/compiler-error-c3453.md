---
title: "コンパイラ エラー C3453 | Microsoft Docs"
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
  - "C3453"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3453"
ms.assetid: dbefdbcf-f697-4239-b7a5-1d99b85e9e7f
caps.latest.revision: 5
caps.handback.revision: 5
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# コンパイラ エラー C3453
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'attribute': 修飾子 'assembly' が一致しなかったため、属性は適用されませんでした  
  
 アセンブリ レベルまたはモジュール レベルの属性は、スタンドアロンの命令としてのみ指定できます。  
  
## 使用例  
 次の例では C3453 が生成されます。  
  
```  
// C3453.cpp // compile with: /clr /c [assembly:System::CLSCompliant(true)]   // C3453 // try the following line instead // [assembly:System::CLSCompliant(true)]; ref class X {};  
```