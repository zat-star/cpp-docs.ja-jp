---
title: "コンパイラ エラー C3531 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C3531
dev_langs:
- C++
helpviewer_keywords:
- C3531
ms.assetid: 2bdb9fdc-9ddf-403e-8b92-02763d434487
caps.latest.revision: 6
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 7753e30e305b7b36adc3b4d2b535f755fa455bdd
ms.contentlocale: ja-jp
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-error-c3531"></a>コンパイラ エラー C3531
'symbol': 型持つにはは、'auto' が含まれていますシンボルは、initializer を持つ必要があります。  
  
 指定された変数の初期化子式ではありません。  
  
### <a name="to-correct-this-error"></a>このエラーを解決するには  
  
1.  変数を宣言する場合、等号 (=) 構文を使用する単純な代入など、初期化子式を指定します。  
  
## <a name="example"></a>例  
 次の例では C3531 のため変数`x1`、 `y1, y2, y3`、および`z2`は初期化されていません。  
  
```  
// C3531.cpp  
// Compile with /Zc:auto  
int main()  
{  
   auto x1;                  // C3531  
   auto y1, y2, y3;          // C3531  
   auto z1 = 1, z2, z3 = -1; // C3531  
   return 0;  
}  
```  
  
## <a name="see-also"></a>関連項目  
 [auto キーワード](../../cpp/auto-keyword.md)
