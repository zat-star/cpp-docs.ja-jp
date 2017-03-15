---
title: "コンパイラ エラー C2514 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2514"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2514"
ms.assetid: 4b7085e5-6714-4261-80b7-bc72e64ab3e8
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# コンパイラ エラー C2514
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'class' : クラスにコンストラクターが定義されていません。  
  
 クラス、構造体、または共用体には、インスタンス化に使用するパラメーターと一致するパラメーター リストを含むコンストラクターがありません。  
  
 クラスをインスタンス化できるためには、クラスが完全に宣言されていることが必要です。  
  
 次の例では警告 C2514 が生成されます。  
  
```  
// C2514.cpp  
// compile with: /c  
class f;  
  
class g {  
public:  
    g (int x);  
};  
  
class fmaker {  
   f *func1() {  
      return new f(2);   // C2514  
   }  
  
   g *func2() {  
      return new g(2);   // OK  
   }  
};   
```