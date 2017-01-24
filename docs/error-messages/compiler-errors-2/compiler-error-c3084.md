---
title: "コンパイラ エラー C3084 | Microsoft Docs"
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
  - "C3084"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3084"
ms.assetid: 0362cb70-e24e-476f-a24d-8f5bb97c3afd
caps.latest.revision: 12
caps.handback.revision: 12
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# コンパイラ エラー C3084
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'function': ファイナライザーまたはデストラクターを 'keyword' にすることはできません。  
  
 ファイナライザーまたはデストラクターの宣言が正しくありません。  
  
 たとえば、デストラクターをシール済みとしてマークすることはできません。  デストラクターは派生型にアクセスできません。  詳細については、「[Explicit Overrides](../../windows/explicit-overrides-cpp-component-extensions.md)」および「[Visual C\+\+ のデストラクターおよびファイナライザー](../../misc/destructors-and-finalizers-in-visual-cpp.md)」を参照してください。  
  
## 使用例  
 次の例では C3084 が生成されます。  
  
```  
// C3084.cpp // compile with: /clr /c ref struct R { protected: !R() sealed;   // C3084 !R() abstract;   // C3084 !R(); };  
```