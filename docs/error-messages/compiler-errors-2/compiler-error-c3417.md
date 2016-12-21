---
title: "コンパイラ エラー C3417 | Microsoft Docs"
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
  - "C3417"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3417"
ms.assetid: 3e7869ea-8948-42fb-ba30-6ccafe499c35
caps.latest.revision: 9
caps.handback.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# コンパイラ エラー C3417
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'メンバー' : 値型は、ユーザー定義された特殊なメンバー関数を含むことはできません  
  
 値型に既定のインスタンス コンストラクター、デストラクター、コピー コンストラクターなどの関数を含めることはできません。  
  
 次の例では警告 C3517 が生成されます。  
  
```  
// C3417.cpp  
// compile with: /clr /c  
value class VC {  
   VC(){}   // C3417  
  
   // OK  
   static VC(){}  
   VC(int i){}  
};  
```