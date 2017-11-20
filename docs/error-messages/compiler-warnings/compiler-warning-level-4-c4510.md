---
title: "コンパイラの警告 (レベル 4) C4510 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C4510
dev_langs: C++
helpviewer_keywords: C4510
ms.assetid: fd28d1d4-ad27-4dad-94c0-9dba46c93180
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 372dd9c789c54a38a5eed2c5f457c518989ede17
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-warning-level-4-c4510"></a>コンパイラの警告 (レベル 4) C4510
'class': 既定のコンス トラクターを生成できませんでした  
  
 コンパイラは、指定したクラスに対して既定のコンス トラクターを生成できませんし、ユーザー定義のコンス トラクターは作成されませんでした。 この型のオブジェクトを作成することはできません。  
  
 コンパイラの既定のコンス トラクターの生成を防ぐことがいくつかの状況があるなど。  
  
-   Const データ メンバーです。  
  
-   参照であるデータ メンバーです。  
  
 これらのメンバーを初期化するクラスのユーザー定義の既定コンス トラクターを作成する必要があります。  
  
 次の例では、C4510 が生成されます。  
  
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