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
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: 3168772cbb7e8127523bc2fc2da5cc9b4f59beb8
ms.openlocfilehash: 839909b108589655000bfe4a76306c8ee9d7339d
ms.contentlocale: ja-jp
ms.lasthandoff: 02/24/2017

---
# <a name="compiler-error-c2422"></a>コンパイラ エラー C2422
'オペランド' に無効なセグメントの上書き  
  
 インライン アセンブラー コードでは、オペランドに対してセグメント オーバーライド演算子 (:)  以下の原因が考えられます。  
  
-   演算子の直前のレジスタは、セグメント レジスタではありません。  
  
-   演算子の直前のレジスタは、オペランド内の唯一のセグメント レジスタではありません。  
  
-   間接演算子 (角かっこ) セグメント オーバーライド演算子が表示されます。  
  
-   次のセグメント オーバーライド演算子式は、即時のオペランドまたはメモリのオペランドではありません。  
  
 次の例では、c2422 エラーが生成されます。  
  
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
