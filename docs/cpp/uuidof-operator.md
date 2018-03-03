---
title: "_ _uuidof 演算子 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- __LIBID_cpp
- __uuidof_cpp
dev_langs:
- C++
helpviewer_keywords:
- __uuidof keyword [C++]
- __LIBID_ keyword [C++]
ms.assetid: badfe709-809b-4b66-ad48-ee35039d25c6
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: c5d83f99b40e6eb897212fbcfb03c01b4f6b55e3
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="uuidof-operator"></a>__uuidof 演算子
**Microsoft 固有の仕様**  
  
 式にアタッチされている GUID を取得します。  
  
## <a name="syntax"></a>構文  
  
```  
  
      __uuidof (  
   expression   
)  
```  
  
## <a name="remarks"></a>コメント  
 *式*型名、ポインター、参照、またはその型の配列を使用できますが、これらの型、またはこれらの型の変数に特化したテンプレートです。 引数は、アタッチされた GUID を見つけるためにコンパイラが使用できる限り有効です。  
  
 ときに、この組み込みの特殊なケースか**0**または**NULL**引数として提供されています。 この場合、`__uuidof` はゼロで構成された GUID を返します。  
  
 このキーワードを使用すると、次のものにアタッチされている GUID を抽出できます。  
  
-   オブジェクト、 [uuid](../cpp/uuid-cpp.md)拡張属性。  
  
-   作成されたライブラリ ブロック、[モジュール](../windows/module-cpp.md)属性。  
  
> [!NOTE]
>  デバッグ ビルドでは、`__uuidof` は常にオブジェクトを動的に (実行時に) 初期化します。 リリース ビルドでは、`__uuidof` は静的に (コンパイル時に) オブジェクトを初期化できます。  
  
## <a name="example"></a>例  
 次のコード (ole32.lib でコンパイル) は、module 属性で作成されたライブラリ ブロックの uuid を表示します。  
  
```  
// expre_uuidof.cpp  
// compile with: ole32.lib  
#include "stdio.h"  
#include "windows.h"  
  
[emitidl];  
[module(name="MyLib")];  
[export]  
struct stuff {  
   int i;  
};  
  
int main() {  
   LPOLESTR lpolestr;  
   StringFromCLSID(__uuidof(MyLib), &lpolestr);  
   wprintf_s(L"%s", lpolestr);  
   CoTaskMemFree(lpolestr);  
}  
```  
  
## <a name="comments"></a>コメント  
 ここで、ライブラリ名は不要になったスコープ内の場合、__LIBID を使用することができます\_の代わりに`__uuidof`です。 例:  
  
```  
StringFromCLSID(__LIBID_, &lpolestr);  
```  
  
 **Microsoft 固有の仕様はここまで**  
  
## <a name="see-also"></a>参照  
 [単項演算子を含む式](../cpp/expressions-with-unary-operators.md)   
 [キーワード](../cpp/keywords-cpp.md)