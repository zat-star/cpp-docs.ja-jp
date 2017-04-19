---
title: "&lt;hash_set&gt; 関数 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- hash_set/std::swap
- hash_set/std::swap (hash_multiset)
ms.assetid: 557a0162-3728-4537-97dc-f9f6cc7ece94
caps.latest.revision: 7
manager: ghogen
translationtype: Machine Translation
ms.sourcegitcommit: 3168772cbb7e8127523bc2fc2da5cc9b4f59beb8
ms.openlocfilehash: 1238f4a4e75f13ccd660554de8c49646549bc2cc
ms.lasthandoff: 02/24/2017

---
# <a name="lthashsetgt-functions"></a>&lt;hash_set&gt; 関数
|||  
|-|-|  
|[swap](#swap)|[swap (hash_multiset)](#swap__hash_multiset_)|  
  
##  <a name="swap"></a>  swap  
  
> [!NOTE]
>  この API は、互換性のために残されています。 代わりに、[unordered_set クラス](../standard-library/unordered-set-class.md)を使用してください。  
  
 2 つの hash_set の要素を交換します。  
  
```
void swap(
    hash_set <Key, Traits, Allocator>& left,
    hash_set <Key, Traits, Allocator>& right);
```  
  
### <a name="parameters"></a>パラメーター  
 `right`  
 交換する要素を提供する hash_set (hash_set `left` の要素と要素を交換する hash_set)。  
  
 `left`  
 要素が hash_set `right` の要素と交換される hash_set。  
  
### <a name="remarks"></a>コメント  
 `swap` テンプレート関数は、コンテナー クラス hash_set に特化したアルゴリズムであり、メンバー関数 `left``.`[swap](../standard-library/hash-set-class.md#hash_set__swap)(`right`) を実行します。 これは、コンパイラによる関数テンプレートの部分的な順序付けのインスタンスです。 テンプレートと関数呼び出しの照合が一意にならないようにテンプレート関数がオーバーロードされた場合、コンパイラは、最も特化したバージョンのテンプレート関数を選択します。 テンプレート関数の一般的なバージョン  
  
 **template \<class T> void swap(T&, T&),**  
  
 は、algorithm クラスにあり、代入によって機能し、処理は低速です。 各コンテナー内の特化バージョンのほうが、コンテナー クラスの内部表現で使用できるため大幅に高速になります。  
  
 Visual C++ .NET 2003 では、[<hash_map>](../standard-library/hash-map.md) ヘッダー ファイルと [<hash_set>](../standard-library/hash-set.md) ヘッダー ファイルのメンバーは、std 名前空間に存在しなくなりましたが、stdext 名前空間に移動されました。 詳細については、「[The stdext 名前空間](../standard-library/stdext-namespace.md)」をご覧ください。  
  
### <a name="example"></a>例  
  `swap` のテンプレート バージョンの使用例については、メンバー クラス [hash_set::swap](../standard-library/hash-set-class.md#hash_set__swap) のコード例をご覧ください。  
  
##  <a name="swap__hash_multiset_"></a> swap (hash_multiset)  
  
> [!NOTE]
>  この API は、互換性のために残されています。 代わりに、[unordered_set クラス](../standard-library/unordered-set-class.md)を使用してください。  
  
 2 つの hash_multiset の要素を交換します。  
  
```
void swap(hash_multiset <Key, Traits, Allocator>& left, hash_multiset <Key, Traits, Allocator>& right);
```  
  
### <a name="parameters"></a>パラメーター  
 `right`  
 交換する要素を提供する hash_multiset (hash_multiset `left` の要素と要素を交換する hash_multiset)。  
  
 `left`  
 要素が hash_multiset `right` の要素と交換される hash_multiset。  
  
### <a name="remarks"></a>コメント  
 `swap` テンプレート関数は、コンテナー クラス hash_multiset に特化したアルゴリズムであり、メンバー関数 `left``.`[swap](../standard-library/hash-multiset-class.md#hash_multiset__swap)(`right`) を実行します。 これは、コンパイラによる関数テンプレートの部分的な順序付けのインスタンスです。 テンプレートと関数呼び出しの照合が一意にならないようにテンプレート関数がオーバーロードされた場合、コンパイラは、最も特化したバージョンのテンプレート関数を選択します。 テンプレート関数の一般的なバージョン  
  
 **template \<class T> void swap(T&, T&),**  
  
 は、algorithm クラスにあり、代入によって機能し、処理は低速です。 各コンテナー内の特化バージョンのほうが、コンテナー クラスの内部表現で使用できるため大幅に高速になります。  
  
 Visual C++ .NET 2003 では、[<hash_map>](../standard-library/hash-map.md) ヘッダー ファイルと [<hash_set>](../standard-library/hash-set.md) ヘッダー ファイルのメンバーは、std 名前空間に存在しなくなりましたが、stdext 名前空間に移動されました。 詳細については、「[The stdext 名前空間](../standard-library/stdext-namespace.md)」をご覧ください。  
  
### <a name="example"></a>例  
  `swap` のテンプレート バージョンの使用例については、メンバー クラス [hash_multiset::swap](../standard-library/hash-multiset-class.md#hash_multiset__swap) のコード例をご覧ください。  
  
## <a name="see-also"></a>関連項目  
 [<hash_set>](../standard-library/hash-set.md)




