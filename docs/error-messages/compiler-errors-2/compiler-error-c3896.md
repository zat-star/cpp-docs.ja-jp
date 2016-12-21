---
title: "コンパイラ エラー C3896 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C3896"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3896"
ms.assetid: eb8be0f6-5b4e-4d71-8285-8a2a94f8ba29
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# コンパイラ エラー C3896
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'メンバー' : 正しくない初期化子です。このリテラル データ メンバーは 'nullptr' と共にのみ初期化できます  
  
 [literal](../../windows/literal-cpp-component-extensions.md) データ メンバーが正しく初期化されていません。詳細については、「[nullptr](../../windows/nullptr-cpp-component-extensions.md)」を参照してください。  
  
 次の例では警告 C3896 が生成されます。  
  
```  
// C3896.cpp  
// compile with: /clr /c  
ref class R{};  
  
value class V {  
   literal R ^ r = "test";   // C3896  
   literal R ^ r2 = nullptr;   // OK  
};  
```