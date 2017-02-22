---
title: "コンパイラ エラー C2533 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2533"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2533"
ms.assetid: 5b335652-076c-4824-87c8-a741f64a3ce0
caps.latest.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 11
---
# コンパイラ エラー C2533
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'identifier': コンストラクターの宣言に戻り値の型が含まれています。  
  
 コンストラクターに戻り値の型を指定することはできません \(戻り値の型が `void` であっても\)。  
  
 このエラーの一般的な原因は、クラス定義の末尾と最初のコンストラクターの実装の間にセミコロンがないことです。  コンパイラはクラスをコンストラクター関数の戻り値の型の定義として認識し、C2533 を生成します。  
  
 次の例では、C2533 を生成し、その修正方法を示しています。  
  
```  
// C2533.cpp  
// compile with: /c  
class X {  
public:  
   X();     
};  
  
int X::X() {}   // C2533 - constructor return type not allowed  
X::X() {}   // OK - fix by using no return type  
```