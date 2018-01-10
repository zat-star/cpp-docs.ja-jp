---
title: "ビット演算子包含的 OR 演算子: | |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- bitor
- '|'
dev_langs: C++
helpviewer_keywords:
- OR operator [C++], bitwise inclusive
- bitwise operators [C++], OR operator
- inclusive OR operator
- '| operator'
ms.assetid: 4c8a6a68-d828-447d-875a-aedb4ce3aa9a
caps.latest.revision: "7"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: eaef650cc747cdb9e628ae3b786bc1c1e21b5bdf
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="bitwise-inclusive-or-operator-"></a>ビット処理包括的 OR 演算子: |
## <a name="syntax"></a>構文  
  
```  
  
expression   
|  
 expression  
  
```  
  
## <a name="remarks"></a>コメント  
 ビットごとの包括的 OR 演算子 (**&#124;**)、2 番目のオペランドの対応するビットを最初のオペランドの各ビットと比較します。 どちらかのビットが 1 の場合、対応する結果のビットは 1 に設定されます。 それ以外の場合は、対応する結果ビットが 0 に設定されます。  
  
 ビットごとの包括的 OR 演算子のオペランドは両方とも整数型である必要があります。 通常の算術変換は、「[標準変換](standard-conversions.md)オペランドに適用されます。  
  
## <a name="operator-keyword-for-124"></a>演算子キーワード &#124;です。  
 `bitor`演算子に相当するテキストは、 **&#124;**です。 アクセスする方法を次の 2 つが、`bitor`をプログラムで演算子: ヘッダー ファイルをインクルード`iso646.h`、コンパイル時に、または、 [/Za](../build/reference/za-ze-disable-language-extensions.md) (言語の拡張機能を無効にする) コンパイラ オプション。  
  
## <a name="example"></a>例  
  
```  
// expre_Bitwise_Inclusive_OR_Operator.cpp  
// compile with: /EHsc  
// Demonstrate bitwise inclusive OR  
#include <iostream>  
using namespace std;  
  
int main() {  
   unsigned short a = 0x5555;      // pattern 0101 ...  
   unsigned short b = 0xAAAA;      // pattern 1010 ...  
  
   cout  << hex << ( a | b ) << endl;   // prints "ffff" pattern 1111 ...  
}  
```  
  
## <a name="see-also"></a>参照  
 [C++ 組み込み演算子、優先順位と結合規則](../cpp/cpp-built-in-operators-precedence-and-associativity.md)   
 [C ビット処理演算子](../c-language/c-bitwise-operators.md)

