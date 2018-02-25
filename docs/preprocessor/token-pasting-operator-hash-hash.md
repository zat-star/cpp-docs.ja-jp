---
title: "トークン連結演算子 (#) |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- '##'
dev_langs:
- C++
helpviewer_keywords:
- preprocessor, operators
- '## preprocessor operator'
ms.assetid: 4f173503-990f-4bff-aef3-ec4d1f1458ef
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: d3a8c2cef3560a6823314a4edb2cba78994864ce
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/23/2018
---
# <a name="token-pasting-operator-"></a>トークン連結演算子 (##)
二重シャープ記号つまり"トークン連結演算子 (**##**)、両方のオブジェクトのようなと関数に似たマクロで使用されて、「マージ」演算子と呼ばれることがあります。 この演算子を使用すると、別々のトークンを 1 つのトークンに結合できます。そのため、これをマクロ定義の最初または最後のトークンにすることはできません。  
  
 マクロ定義の仮パラメーターの前または後ろにトークン連結演算子がある場合、仮パラメーターは展開されていない実引数に即座に置き換えられます。 引数に対するマクロ展開が置換の前に行われることはありません。  
  
 次に、発生するたびにトークン連結演算子*トークン文字列*が削除され、前と後に続くトークンが連結されたとします。 結果のトークンは有効なトークンである必要があります。 有効であれば、トークンがスキャンされ、マクロ名を表す場合は置換が可能かどうかが確認されます。 この識別子は、置換前のプログラム内で連結されたトークンを認識するための名前になります。 各トークンは、他のどこか、つまり、プログラム内またはコンパイラのコマンド ラインで定義された特定のトークンを表します。 演算子の前または後の空白は、省略可能です。  
  
 この例は、プログラムの出力を指定するときの、文字列化演算子とトークン連結演算子の両方の使用方法を示しています。  
  
```  
#define paster( n ) printf_s( "token" #n " = %d", token##n )  
int token9 = 9;  
```  
  
 マクロが次のような数値引数で呼び出された場合、  
  
```  
paster( 9 );  
```  
  
 このマクロは次のようになり、  
  
```  
printf_s( "token" "9" " = %d", token9 );  
```  
  
 さらに、次のようになります。  
  
```  
printf_s( "token9 = %d", token9 );  
```  
  
## <a name="example"></a>例  
  
```  
// preprocessor_token_pasting.cpp  
#include <stdio.h>  
#define paster( n ) printf_s( "token" #n " = %d", token##n )  
int token9 = 9;  
  
int main()  
{  
   paster(9);  
}  
```  
  
```Output  
token9 = 9  
```  
  
## <a name="see-also"></a>参照  
 [プリプロセッサ演算子](../preprocessor/preprocessor-operators.md)