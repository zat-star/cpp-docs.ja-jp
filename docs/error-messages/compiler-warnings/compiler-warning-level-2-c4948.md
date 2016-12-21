---
title: "コンパイラの警告 (レベル 2) C4948 | Microsoft Docs"
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
  - "C4948"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4948"
ms.assetid: d006cb17-754a-4c70-ba7f-c3200e2cd8fa
caps.latest.revision: 9
caps.handback.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# コンパイラの警告 (レベル 2) C4948
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'accessor' の戻り値の型が、対応する setter の最後のパラメーターに一致しません。  
  
 インデックス付きプロパティで取得および設定されるデータ型に不一致が見つかりました。  
  
 C4948 が発生するのは **\/clr:oldSyntax** を使用した場合だけです。  
  
 次の例では警告 C4948 が生成されます。  
  
```  
// C4948.cpp  
// compile with: /clr:oldSyntax /LD /W2  
  
__gc class MyClass  
{  
   int prop __nogc [2];  
   public:  
  
      __property int get_P(int i)  
      // try the following line instead  
      // __property char get_P(int i)  
      {  
         return prop[i];  
      }  
  
      __property void set_P(int i, char c)  
      {  
         prop[i] = c;  
      }  
};   // C4948  
```