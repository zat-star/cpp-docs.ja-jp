---
title: "コンパイラ エラー C2793 | Microsoft Docs"
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
  - "C2793"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2793"
ms.assetid: ce35f4e8-c357-40ca-95c4-15ff001ad69d
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# コンパイラ エラー C2793
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'token' : 予期しないトークンが '::' の後ろにあります、識別子またはキーワード 'operator' が必要です。  
  
 `__super::` の後に使用できるトークンは、識別子またはキーワード `operator` だけです。  
  
 次の例では C2793 エラーが生成されます。  
  
```  
// C2793.cpp  
struct B {  
   void mf();  
};  
  
struct D : B {  
   void mf() {  
      __super::(); // C2793  
   }  
};  
```