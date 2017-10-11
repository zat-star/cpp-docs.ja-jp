---
title: "コンパイラ エラー C2422 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2422
dev_langs:
- C++
helpviewer_keywords:
- C2422
ms.assetid: ef0ec302-4028-4778-b134-0b8cea4bcad9
caps.latest.revision: 9
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 65412576c3c1a5e6b8205652d826d0eca6d222e6
ms.contentlocale: ja-jp
ms.lasthandoff: 10/09/2017

---
# <a name="compiler-error-c2422"></a>コンパイラ エラー C2422
'のオペランド' で誤ったセグメント オーバーライド  
  
 インライン アセンブラー コードで、オペランドに対してセグメント オーバーライド演算子 (:)  以下の原因が考えられます。  
  
-   演算子の直前のレジスタは、セグメント レジスタではありません。  
  
-   演算子の直前のレジスタは、オペランド内の唯一のセグメント レジスタではありません。  
  
-   間接演算子 (かっこ) 内のセグメント オーバーライド演算子が表示されます。  
  
-   セグメント オーバーライド演算子の後の式は、イミディ エイトのオペランドまたはメモリ オペランドではありません。  
  
 次の例では、C2422 が生成されます。  
  
```  
// C2422.cpp  
// processor: x86  
int main() {  
   _asm {  
      mov AX, [BX:ES]   // C2422  
      mov AX, ES   // OK  
   }  
}  
```
