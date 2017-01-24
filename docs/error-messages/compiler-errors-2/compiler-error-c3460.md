---
title: "コンパイラ エラー C3460 | Microsoft Docs"
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
  - "C3460"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3460"
ms.assetid: adbf8775-10ca-4654-acdf-58dd765351cd
caps.latest.revision: 6
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# コンパイラ エラー C3460
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'type': 転送できるのはユーザー定義型のみです  
  
 詳細については、「[Type Forwarding \(C\+\+\/CLI\)](../../windows/type-forwarding-cpp-cli.md)」を参照してください。  
  
## 使用例  
 コンポーネントを作成する例を次に示します。  
  
```  
// C3460.cpp // compile with: /LD /clr public ref class R {};  
```  
  
## 使用例  
 次の例では C3460 が生成されます。  
  
```  
// C3460_b.cpp // compile with: /clr /c #using "C3460.dll" [assembly:TypeForwardedTo(int::typeid)];   // C3460 [assembly:TypeForwardedTo(R::typeid)];  
```