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
caps.latest.revision: 11
author: mikeblome
ms.author: mblome
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
ms.translationtype: HT
ms.sourcegitcommit: 6ffef5f51e57cf36d5984bfc43d023abc8bc5c62
ms.openlocfilehash: 9f899add9a1306344a10840220f3b7504e917d91
ms.contentlocale: ja-jp
ms.lasthandoff: 09/25/2017

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
  
## <a name="see-also"></a>関連項目  
 [キーワード](../cpp/keywords-cpp.md)
