---
title: "コンパイラ エラー C2178 |Microsoft ドキュメント"
ms.custom: 
ms.date: 05/08/2017
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C2178
dev_langs:
- C++
helpviewer_keywords:
- C2178
ms.assetid: 79a14158-17f3-4221-bd06-9d675c49cef4
caps.latest.revision: 0
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Machine Translation
ms.sourcegitcommit: 128bd124c2536d86c8b673b54abc4b5505526b41
ms.openlocfilehash: 96232cdb52fc84a90c768fa23b8a98da913c7982
ms.contentlocale: ja-jp
ms.lasthandoff: 05/10/2017

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

