---
title: "コンパイラ エラー C3898 | Microsoft Docs"
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
  - "C3898"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3898"
ms.assetid: d9a90df6-87e4-4fe7-ab01-c226ee86bf10
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# コンパイラ エラー C3898
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'var' : '型' データ メンバーは、マネージ型のメンバーにのみなることができます  
  
 [initonly](../../dotnet/initonly-cpp-cli.md) データ メンバーがネイティブなクラスで宣言されています。`initonly` データ メンバーが宣言できるのは、CLR クラスだけです。  
  
 次の例では警告 C3898 が生成されます。  
  
```  
// C3898.cpp  
// compile with: /clr  
struct Y1 {  
   initonly  
   static int data_var = 9;   // C3898  
};  
```  
  
 解決方法 :  
  
```  
// C3898b.cpp  
// compile with: /clr /c  
ref struct Y1 {  
   initonly  
   static int data_var = 9;  
};  
```