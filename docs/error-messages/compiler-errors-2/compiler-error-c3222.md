---
title: "コンパイラ エラー C3222 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C3222"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3222"
ms.assetid: 5624bde8-2fd0-4b8b-92ce-5dfbaf91cf93
caps.latest.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 10
---
# コンパイラ エラー C3222
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'parameter': ジェネリック関数またはマネージあるいは WinRT 型のメンバー関数に対して、既定引数を宣言できません  
  
 既定の引数を持つメソッド パラメーターを宣言することは許可されていません。  メソッドのオーバーロードは、この問題を回避する方法の 1 つです。  つまり、同じ名前でパラメーターを持たないメソッドを定義し、メソッド本体で変数を初期化します。  
  
 次の例では C3222 が生成されます。  
  
```  
// C3222_2.cpp  
// compile with: /clr  
public ref class G {  
   void f( int n = 0 );   // C3222  
};  
```  
  
 次の例では C3222 が生成されます。  
  
```  
// C3222.cpp  
// compile with: /clr:oldSyntax  
public __gc class G {  
   void f( int n = 0 );   // C3222  
};  
```