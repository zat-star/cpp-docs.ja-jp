---
title: "コンパイラの警告 (レベル 3) C4316 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C4316
dev_langs:
- C++
helpviewer_keywords:
- C4316
ms.assetid: 10371f01-aeb8-40ac-a290-59e63efa5ad4
caps.latest.revision: 5
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
ms.openlocfilehash: 5647c3ca9dbbd854c83398820575137c4032d3c6
ms.contentlocale: ja-jp
ms.lasthandoff: 02/24/2017

---
# <a name="compiler-warning-level-3-c4316"></a>コンパイラの警告 (レベル 3) C4316
ヒープで割り当てられているオブジェクトが、この型にアラインされていない可能性があります。  
  
 `operator new` を使用して割り当てられたオブジェクトがオーバーアラインされている場合は、このオブジェクトにアラインメントが指定されていない可能性があります。 オーバーライド[new 演算子](../../c-runtime-library/operator-new-crt.md)と[delete 演算子](../../c-runtime-library/operator-delete-crt.md)のアラインされた割り当てルーチンを使用するようオーバーア ラインされた型 — たとえば、 [_aligned_malloc](../../c-runtime-library/reference/aligned-malloc.md)と[_aligned_free](../../c-runtime-library/reference/aligned-free.md)します。 次の例では、C4316 が生成されます。  
  
```cpp  
// C4316.cpp  
// Test: cl /W3 /c C4316.cpp  
  
__declspec(align(32)) struct S {}; // C4324  
  
int main() {  
    new S; // C4316  
}  
```
