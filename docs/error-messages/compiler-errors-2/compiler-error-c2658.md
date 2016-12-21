---
title: "コンパイラ エラー C2658 | Microsoft Docs"
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
  - "C2658"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2658"
ms.assetid: 638368e8-7893-4a14-abec-13c768a9543a
caps.latest.revision: 9
caps.handback.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# コンパイラ エラー C2658
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'member': 無名構造体または共用体での再定義。  
  
 2 つの無名構造体または無名共用体に、識別子は同じで型の異なるメンバー宣言が含まれています。  [\/Za](../../build/reference/za-ze-disable-language-extensions.md) を指定すると、識別子と型が同じメンバーについてもこのエラーが返されます。  
  
 次の例では警告 C2658 が生成されます。  
  
```  
// C2658.cpp  
// compile with: /c  
struct X {  
   union { // can be struct too  
      int i;  
   };  
   union {  
      int i;   // Under /Za, C2658  
      // int i not needed here because it is defined in the first union  
   };  
};  
  
struct Z {  
   union {  
      char *i;  
   };  
  
   union {  
      void *i;   // C2658 redefinition of 'i'  
      // try the following line instead  
      // void *ii;  
   };  
};  
```