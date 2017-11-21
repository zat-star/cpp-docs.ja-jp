---
title: "コンパイラ エラー C2178 |Microsoft ドキュメント"
ms.custom: 
ms.date: 05/08/2017
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: C2178
dev_langs: C++
helpviewer_keywords: C2178
ms.assetid: 79a14158-17f3-4221-bd06-9d675c49cef4
caps.latest.revision: "0"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: facb255b0c53a3de0e1d5c9f90de5835b25e3c32
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c2178"></a>コンパイラ エラー C2178  
  
'*識別子*'で宣言することはできません'*指定子*' 指定子  
  
A`mutable`指定子では使用されて、宣言指定子はこのコンテキストで許可されていません。  
  
`mutable`指定子のクラス データ メンバーの名前にのみ適用でき、宣言された名前には適用できません`const`または`static`メンバーを参照するには適用できません。  
  
## <a name="example"></a>例  
  
次の例では、どのように C2178 が発生し、その修正方法を示します。  
  
```  
// C2178.cpp
// compile with: cl /c /W4 C2178.cpp

class S {
    mutable const int i; // C2178
    // To fix, declare either const or mutable, not both.
};

mutable int x = 4; // C2178
// To fix, remove mutable keyword
```  
