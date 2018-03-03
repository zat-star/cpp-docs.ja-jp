---
title: "_ _Asm ブロック内の演算子を使用して |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- brackets [ ]
- brackets [ ], __asm blocks
- __asm keyword [C++], operators
- square brackets [ ], __asm blocks
- operators [C++], using in __asm blocks
- square brackets [ ]
ms.assetid: a26ccfd4-40ae-4a61-952f-c417982aa8dd
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: ca8ac739793c81ef18f8657cbf53c9cb018b3e38
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="using-operators-in-asm-blocks"></a>__asm ブロックでの演算子の使用
## <a name="microsoft-specific"></a>Microsoft 固有の仕様  
 `__asm`ブロックがなど C または C++ の特定の演算子を使用することはできません、  **<<** 演算子。 ただし、演算子とで共有される C MASM、ように、\*演算子は、アセンブリ言語の演算子として解釈されます。 たとえば、外部、`__asm`ブロック、角かっこ (**[]**) C は、配列内の要素のサイズを自動的にスケーリング配列の添字を囲むとして解釈されます。 内部、`__asm`ブロック、任意のデータ オブジェクトまたはラベル (配列だけでなく) から、スケールなしのバイト オフセットを生成、MASM インデックス演算子見なされます。 次のコードは、違いを示しています。  
  
```  
int array[10];  
  
__asm mov array[6], bx ;  Store BX at array+6 (not scaled)  
  
array[6] = 0;         /* Store 0 at array+24 (scaled) */  
```  
  
 最初に参照`array`拡大縮小されませんが、2 つ目はします。 使用できるに注意してください、**型**定数に基づいてスケーリングを実現するために演算子。 たとえば、次のステートメントは同等です。  
  
```  
__asm mov array[6 * TYPE int], 0 ; Store 0 at array + 24  
  
array[6] = 0;                   /* Store 0 at array + 24 */  
```  
  
 **Microsoft 固有の仕様はここまで**  
  
## <a name="see-also"></a>参照  
 [__asm ブロックでの C または C++ の使用](../../assembler/inline/using-c-or-cpp-in-asm-blocks.md)