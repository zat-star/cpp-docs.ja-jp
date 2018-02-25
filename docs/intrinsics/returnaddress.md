---
title: "_ReturnAddress |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- _ReturnAddress
dev_langs:
- C++
helpviewer_keywords:
- _ReturnAddress intrinsic
- ReturnAddress intrinsic
ms.assetid: 7f4a5811-35e6-4f64-ba7c-21203380eeda
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: ae1437d6523b94071a5e7655bfa2e7094d89305a
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/23/2018
---
# <a name="returnaddress"></a>_ReturnAddress
## <a name="microsoft-specific"></a>Microsoft 固有の仕様  
 `_ReturnAddress`組み込みコントロールが呼び出し元に返された後に実行される呼び出し元の関数内の命令のアドレスを提供します。  
  
 次のプログラムと、デバッガーでステップを作成します。 プログラムをステップ実行するから返されるアドレスを確認します。`_ReturnAddress`です。 その後、関数から返された後すぐに、`_ReturnAddress`が、使用される、開いている、[する方法: [逆アセンブル] ウィンドウを使用して](/visualstudio/debugger/how-to-use-the-disassembly-window)と実行される次の命令のアドレスがから返されたアドレスと一致することに注意してください`_ReturnAddress`.  
  
 インライン展開月などの最適化、戻り値のアドレスに影響します。 たとえば、次のサンプル プログラムでコンパイル[/Ob1](../build/reference/ob-inline-function-expansion.md)、`inline_func`は呼び出し元の関数をインラインになります`main`です。 したがってへの呼び出し`_ReturnAddress`から`inline_func`と`main`それぞれ同じ値が生成されます。  
  
 ときに`_ReturnAddress`でコンパイルされたプログラムで使用される[/clr](../build/reference/clr-common-language-runtime-compilation.md)、関数を含む、`_ReturnAddress`呼び出しはネイティブ関数としてコンパイルされます。 含む関数への呼び出しとして関数をコンパイルするときに管理されている`_ReturnAddress`、`_ReturnAddress`期待どおりに動作しない可能性があります。  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー ファイル** \<intrin.h >  
  
## <a name="example"></a>例  
  
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
  
**Microsoft 固有の仕様はここまで**  
  
## <a name="see-also"></a>参照  
 [_AddressOfReturnAddress](../intrinsics/addressofreturnaddress.md)   
 [コンパイラ組み込み関数](../intrinsics/compiler-intrinsics.md)   
 [キーワード](../cpp/keywords-cpp.md)