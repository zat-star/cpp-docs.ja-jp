---
title: "コンパイラの警告 (レベル 1) C4730 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C4730
dev_langs: C++
helpviewer_keywords: C4730
ms.assetid: 11303e3f-162b-4b19-970a-479686123a68
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 334c53b030097dc822451b0e555a51c90e70d904
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-1-c4730"></a>コンパイラの警告 (レベル 1) C4730
'main': _m64 と浮動小数点式が不適切なコードで発生する可能性があります  
  
 関数を使用して[_ _m64](../../cpp/m64.md)と**float**/**二重**型です。 MMX と浮動小数点レジスタは、同じ物理を共有するための登録スペース (ことはできません同時に使用) を使用して`__m64`と**float**/**二重**同じ内の型関数は、データの破損、可能性のある例外の原因になります。  
  
 安全に行う`__m64`、型の 1 つを使用する各命令を指定する型と同じ関数内の浮動小数点型では、 **_m_empty()** (MMX) 用または**_m_femms()** (用 3 dnow!)組み込みです。  
  
 次の例では、C4730 が生成されます。  
  
```  
// C4730.cpp  
// compile with: /W1  
// processor: x86  
#include "mmintrin.h"  
  
void func(double)  
{  
}  
  
int main(__m64 a, __m64 b)  
{  
   __m64 m;  
   double f;  
   f = 1.0;  
   m = _m_paddb(a, b);  
   // uncomment the next line to resolve C4730  
   // _m_empty();  
   func(f * 3.0);   // C4730  
}  
```