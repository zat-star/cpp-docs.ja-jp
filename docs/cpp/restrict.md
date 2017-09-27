---
title: "制限 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- restrict
- restrict_cpp
dev_langs:
- C++
helpviewer_keywords:
- __declspec keyword [C++], restrict
- restrict __declspec keyword
ms.assetid: f39cf632-68d8-4362-a497-2d4c15693689
caps.latest.revision: 9
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
ms.openlocfilehash: 2d1cdbff84966e7926b30ef70c40581cc3801a93
ms.contentlocale: ja-jp
ms.lasthandoff: 09/25/2017

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
  
## <a name="see-also"></a>関連項目  
 [_ _declspec](../cpp/declspec.md)   
 [キーワード](../cpp/keywords-cpp.md)
