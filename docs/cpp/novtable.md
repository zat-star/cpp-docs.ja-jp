---
title: novtable |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- novtable_cpp
dev_langs:
- C++
helpviewer_keywords:
- novtable __declspec keyword
- __declspec keyword [C++], novtable
ms.assetid: cfef09c5-8c1e-4b14-8a72-7d726ded4484
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 283ff09c320b67686e353f0497c665828cd8b5d0
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
---
# <a name="novtable"></a>novtable
## <a name="microsoft-specific"></a>Microsoft 固有の仕様  
 これは `__declspec` 拡張属性です。  
  
 この形式の `__declspec` は任意のクラス宣言に適用できますが、純粋なインターフェイス クラス (それ自体はインスタンス化されないクラス) だけに適用してください。 `__declspec` は、クラスのコンストラクターおよびデストラクター内の vfptr を初期化するコードをコンパイラが生成することを阻止します。 多くの場合、これは、クラスに関連付けられている vtable への参照のみを削除するので、リンカーはこれを削除します。 この形式の `__declspec` を使用すると、コード サイズが大幅に削減されます。  
  
 `novtable` でマークされたクラスをインスタンス化してから、クラス メンバーにアクセスしようとすると、アクセス違反 (AV) となります。  
  
## <a name="example"></a>例  
  
```  
// novtable.cpp  
#include <stdio.h>  
  
struct __declspec(novtable) X {  
   virtual void mf();  
};  
  
struct Y : public X {  
   void mf() {  
      printf_s("In Y\n");  
   }  
};  
  
int main() {  
   // X *pX = new X();  
   // pX->mf();   // Causes a runtime access violation.  
  
   Y *pY = new Y();  
   pY->mf();  
}  
```  
  
```Output  
In Y  
```  
  
**Microsoft 固有の仕様はここまで**  
  
## <a name="see-also"></a>関連項目  
 [__declspec](../cpp/declspec.md)   
 [キーワード](../cpp/keywords-cpp.md)