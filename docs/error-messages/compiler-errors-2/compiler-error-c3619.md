---
title: "コンパイラ エラー C3619 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C3619"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3619"
ms.assetid: 76ae80d0-9fbe-4297-a1ef-b1503377fdcf
caps.latest.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 11
---
# コンパイラ エラー C3619
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

マネージ型または WinRT 型でテンプレートは宣言できません  
  
 クラス テンプレートは、マネージ クラスや WinRT クラスまたはインターフェイスでは使用できません。  
  
 C3619 が発生するのは **\/clr:oldSyntax** を使用した場合だけです。  
  
 次の例では C3619 が生成されます。  
  
```  
// C3619.cpp  
// compile with: /clr:oldSyntax  
#using <mscorlib.dll>  
  
__gc class X {  
   template<typename T> class Y {   // C3619  
   };  
};  
```