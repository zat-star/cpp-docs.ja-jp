---
title: "_variant_t クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- _variant_t
dev_langs:
- C++
helpviewer_keywords:
- _variant_t class [C++], operators
- _variant_t class
- _variant_t class [C++], member functions
- VARIANT object
- VARIANT object [C++], COM encapsulation
ms.assetid: 6a3cbd4e-0ae8-425e-b4cf-ca0df894c93f
caps.latest.revision: 10
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
ms.openlocfilehash: 3c074061955adbb1682bb7d96345a31fcf8f04e7
ms.contentlocale: ja-jp
ms.lasthandoff: 09/25/2017

---
# <a name="variantt-class"></a>_variant_t クラス
**Microsoft 固有の仕様**  
  
 `_variant_t` オブジェクトは、`VARIANT` データ型をカプセル化します。 クラスは、リソース割り当てと解放を管理し、関数を呼び出します**VariantInit**と**VariantClear**をクリックします。  
  
### <a name="construction"></a>構築  
  
|||  
|-|-|  
|[_variant_t](../cpp/variant-t-variant-t.md)|`_variant_t` オブジェクトを構築します。|  
  
### <a name="operations"></a>オペレーション  
  
|||  
|-|-|  
|[添付](../cpp/variant-t-attach.md)|アタッチ、**バリアント**オブジェクトに、`_variant_t`オブジェクト。|  
|[クリア](../cpp/variant-t-clear.md)|カプセル化された消去**バリアント**オブジェクト。|  
|[ChangeType](../cpp/variant-t-changetype.md)|型を変更、`_variant_t`オブジェクトを指定された**VARTYPE**です。|  
|[デタッチ](../cpp/variant-t-detach.md)|カプセル化されたデタッチ**バリアント**オブジェクトからこの`_variant_t`オブジェクト。|  
|[SetString](../cpp/variant-t-setstring.md)|この `_variant_t` オブジェクトに文字列を代入します。|  
  
### <a name="operators"></a>演算子  
  
|||  
|-|-|  
|[演算子 =](../cpp/variant-t-operator-equal.md)|既存の `_variant_t` オブジェクトに新しい値を代入します。|  
|[演算子 = =、! =](../cpp/variant-t-relational-operators.md)|2 つの `_variant_t` オブジェクトを比較して、等しいかどうかを確認します。|  
|[抽出](../cpp/variant-t-extractors.md)|カプセル化されたからデータを抽出**バリアント**オブジェクト。|  
  
**Microsoft 固有の仕様はここまで**  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** comutil.h  
  
 **Lib:** comsuppw.lib または comsuppwd.lib (を参照してください[/Zc:wchar_t (wchar_t をネイティブ型)](../build/reference/zc-wchar-t-wchar-t-is-native-type.md)詳細)  
  
## <a name="see-also"></a>関連項目  
 [コンパイラ COM サポート クラス](../cpp/compiler-com-support-classes.md)
