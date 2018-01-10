---
title: "制限 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: restrict_cpp
dev_langs: C++
helpviewer_keywords:
- __declspec keyword [C++], restrict
- restrict __declspec keyword
ms.assetid: f39cf632-68d8-4362-a497-2d4c15693689
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 24fa0dae15fb0d4dfab8d481c6626c7611295572
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="restrict"></a>restrict
**Microsoft 固有の仕様**  
  
 ポインター型を返し、関数が他のポインターでエイリアス化されないオブジェクトを返すことをコンパイラに伝える関数宣言または関数定義に適用されます。  
  
## <a name="syntax"></a>構文  
  
```  
__declspec(restrict) return_type f();  
```  
  
## <a name="remarks"></a>コメント  
 コンパイラは、`__declspec(restrict)` を反映させます。 たとえば、CRT `malloc` 関数は `__declspec(restrict)` で修飾されるため、`malloc` でメモリ位置に初期化されたポインターも暗黙でエイリアスは設定されません。  
  
 コンパイラは、ポインターが実際にはエイリアス化されていないことを確認しません。 `restrict __declspec` 修飾子で示したポインターにエイリアスがないかどうか確認するのは開発者の責任です。  
  
 変数によく似たセマンティクスは、次を参照してください。 [_ _restrict](../cpp/extension-restrict.md)です。  
  
## <a name="example"></a>例  
 参照してください[noalias](../cpp/noalias.md)使用例については`restrict`します。  
  
 詳細については、C++ AMP の一部だけに制限するキーワードは、次を参照してください。[制限 (C++ AMP)](../cpp/restrict-cpp-amp.md)です。  
  
 **Microsoft 固有の仕様はここまで**  
  
## <a name="see-also"></a>参照  
 [_ _declspec](../cpp/declspec.md)   
 [キーワード](../cpp/keywords-cpp.md)