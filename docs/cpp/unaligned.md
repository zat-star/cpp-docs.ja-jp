---
title: "_ _unaligned |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- __unaligned_cpp
dev_langs:
- C++
helpviewer_keywords:
- __unaligned keyword [C++]
ms.assetid: 0cd83aad-1840-47e3-ad33-59bfcbe6375b
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: da662cf9cbe17539381766d37255e63d958fb7b1
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="unaligned"></a>__unaligned
`__unaligned` 修飾子を使用してポインターを宣言すると、コンパイラは、ポインターがアラインされていないデータを指していると見なします。 その結果、IPF (Itanium Processor Family) コンピューターを対象とするアプリケーションの場合、コンパイラは、アラインされていないデータを 1 バイトずつ読み込むコードを生成します。  
  
## <a name="remarks"></a>コメント  
 `__unaligned`に対する修飾子が正しく、[!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]と[!INCLUDE[vcpritanium](../cpp/includes/vcpritanium_md.md)]コンパイラが、アプリケーションだけに影響を IPF コンピューターを対象とします。 この修飾子は、アドレス指定されたデータのアラインメントのみを対象とします。ポインター自体はアラインされていると見なされます。  
  
 [!INCLUDE[vcpritanium](../cpp/includes/vcpritanium_md.md)]ずれているデータにアクセスして、そのエラー処理にかかる時間によってパフォーマンスが低下した場合に、プロセッサが、アラインメント エラーを生成します。 `__unaligned` 修飾子を使用してプロセッサが 1 バイトずつデータを読み取るようにすることで、エラーを回避してください。 この修飾子は必要ありません[!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]アプリケーションのため、[!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]プロセッサでは、データの不整合を処理せずにエラーが発生します。  
  
 アラインメントの詳細については、次のトピックを参照してください。  
  
-   [align](../cpp/align-cpp.md)  
  
-   [__alignof 演算子](../cpp/alignof-operator.md)  
  
-   [pack](../preprocessor/pack.md)  
  
-   [/Zp (構造体メンバーの配置)](../build/reference/zp-struct-member-alignment.md)  
  
-   [構造体の配置例](../build/examples-of-structure-alignment.md)  
  
## <a name="example"></a>例  
  
```  
// unaligned_keyword.cpp  
// compile with: /c  
// processor: x64 IPF  
#include <stdio.h>  
int main() {  
   char buf[100];  
  
   int __unaligned *p1 = (int*)(&buf[37]);  
   int *p2 = (int *)p1;  
  
   *p1 = 0;   // ok  
  
   __try {  
      *p2 = 0;  // throws an exception  
   }  
   __except(1) {  
      puts("exception");  
   }  
}  
```  
  
## <a name="see-also"></a>参照  
 [キーワード](../cpp/keywords-cpp.md)