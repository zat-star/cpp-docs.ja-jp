---
title: "コンパイラの警告 (レベル 4) C4510 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4510"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4510"
ms.assetid: fd28d1d4-ad27-4dad-94c0-9dba46c93180
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# コンパイラの警告 (レベル 4) C4510
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'class' : 既定のコンストラクターを生成できません。  
  
 指定されたクラスの既定のコンストラクターを生成できず、ユーザー定義コンストラクターは作成されませんでした。  この型のオブジェクトは作成できません。  
  
 コンパイラが既定のコンストラクターを生成できないのは、次のような場合です。  
  
-   定数データ メンバーの場合  
  
-   参照であるデータ メンバーの場合  
  
 このようなメンバーを初期化するクラス用に、ユーザー定義の既定のコンストラクターを作成する必要があります。  
  
 次の例では警告 C4510 が生成されます。  
  
```  
// C4510.cpp  
// compile with: /W4  
struct A {  
   const int i;  
   int &j;  
   A& operator=( const A& ); // C4510 expected  
   // uncomment the following line to resolve this C4510  
   // A(int ii, int &jj) : i(ii), j(jj) {}  
};   // C4510  
  
int main() {  
}  
```