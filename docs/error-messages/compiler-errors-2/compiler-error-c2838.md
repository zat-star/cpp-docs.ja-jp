---
title: "コンパイラ エラー C2838 | Microsoft Docs"
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
  - "C2838"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2838"
ms.assetid: 176b2ad6-7a84-4019-b97e-328866054457
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# コンパイラ エラー C2838
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'member' : メンバー宣言内の限定名が間違っています。  
  
 クラス、構造体、または共用体内で、別のクラス、構造体、または共用体のメンバーを完全限定名で再宣言しています。  
  
 次の例では警告 C2838 が生成されます。  
  
```  
// C2838.cpp  
// compile with: /c  
class Bellini {  
public:  
    void Norma();  
};  
  
class Bottesini {  
   Bellini::Norma();  // C2838  
};  
```