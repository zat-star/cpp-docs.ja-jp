---
title: "_ReturnAddress | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "_ReturnAddress"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_ReturnAddress 組み込み"
  - "ReturnAddress 組み込み"
ms.assetid: 7f4a5811-35e6-4f64-ba7c-21203380eeda
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# _ReturnAddress
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

## Microsoft 固有の仕様 →  
 `_ReturnAddress` の組み込みは呼び出し元に返されるの後で実行される呼び出し元の関数の命令のアドレスを指定します。  
  
 デバッガーでプログラムを通じて次の手順を実行します。  プログラムをステップ実行すると`_ReturnAddress` から返されるアドレスに注意してください。  次に`_ReturnAddress` が使用された関数から返された直後に[方法 : \[逆アセンブル\] ウィンドウを使用する](../Topic/How%20to:%20Use%20the%20Disassembly%20Window.md) を開きアドレスが `_ReturnAddress` で返される実行された一致する次の命令のアドレスことに注意してください。  
  
 インライン展開のような最適化がリターン アドレスに影響する場合があります。  たとえばサンプル プログラムの下の [\/Ob1](../build/reference/ob-inline-function-expansion.md) とコンパイル `inline_func` が呼び出し元の関数に`main` にインライン展開されます。  したがって`inline_func` から `_ReturnAddress` と `main` の呼び出しはそれぞれ同じ値を決定します。  
  
 `_ReturnAddress` が [\/clr](../build/reference/clr-common-language-runtime-compilation.md) でコンパイルされたプログラムで使用される場合 `_ReturnAddress` の呼び出しを含む関数はネイティブ関数としてコンパイルされます。  `_ReturnAddress``_ReturnAddress` を含む関数にマネージ呼び出しとしてコンパイルされた関数が期待どおりに動作しない可能性があります。  
  
## 要件  
 **ヘッダー ファイル** \<intrin.h\>  
  
## 使用例  
  
```  
// compiler_intrinsics__ReturnAddress.cpp  
#include <stdio.h>  
#include <intrin.h>  
  
#pragma intrinsic(_ReturnAddress)  
  
__declspec(noinline)  
void noinline_func(void)  
{  
   printf("Return address from %s: %p\n", __FUNCTION__, _ReturnAddress());  
}  
  
__forceinline  
void inline_func(void)  
{  
   printf("Return address from %s: %p\n", __FUNCTION__, _ReturnAddress());  
}  
  
int main(void)  
{  
   noinline_func();   
   inline_func();  
   printf("Return address from %s: %p\n", __FUNCTION__, _ReturnAddress());  
  
   return 0;  
}  
```  
  
## 終了 Microsoft 固有の仕様→  
  
## 参照  
 [\_AddressOfReturnAddress](../intrinsics/addressofreturnaddress.md)   
 [コンパイラ組み込み](../intrinsics/compiler-intrinsics.md)   
 [C\+\+ キーワード](../cpp/keywords-cpp.md)