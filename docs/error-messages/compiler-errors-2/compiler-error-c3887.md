---
title: "コンパイラ エラー C3887 | Microsoft Docs"
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
  - "C3887"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3887"
ms.assetid: a7e82426-ef99-437b-9562-2822004e18fe
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# コンパイラ エラー C3887
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'var' : リテラル データ メンバーの初期化子は定数指揮でなければなりません  
  
 [literal](../../windows/literal-cpp-component-extensions.md) データ メンバーは、定数式でのみ初期化できます。  
  
 次の例では警告 C3887 が生成されます。  
  
```  
// C3887.cpp  
// compile with: /clr  
ref struct Y1 {  
   static int i = 9;  
   literal  
   int staticConst = i;   // C3887  
};  
```  
  
 解決方法 :  
  
```  
// C3887b.cpp  
// compile with: /clr /c  
ref struct Y1 {  
   literal  
   int staticConst = 9;  
};  
```