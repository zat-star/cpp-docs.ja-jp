---
title: "コンパイラ エラー C3462 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C3462"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3462"
ms.assetid: 56b75f35-9fad-42d9-a969-eeca5d709bec
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# コンパイラ エラー C3462
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'type': インポートされた型のみを転送することができます  
  
 TypeForwardedTo 属性は、参照されたメタデータ内の型に適用する必要があります。  
  
 詳細については、「[Type Forwarding \(C\+\+\/CLI\)](../../windows/type-forwarding-cpp-cli.md)」を参照してください。  
  
## 使用例  
 コンポーネントを作成する例を次に示します。  
  
```  
// C3462.cpp // compile with: /clr /LD public ref class R {};  
```  
  
## 使用例  
 次の例では C3462 が生成されます。  
  
```  
// C3462b.cpp // compile with: /clr /c #using "C3462.dll" ref class N {}; [assembly:TypeForwardedTo(N::typeid)];   // C3462 [assembly:TypeForwardedTo(R::typeid)];  
```