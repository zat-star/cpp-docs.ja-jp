---
title: "&lt;hash_map&gt; 関数 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 28748cd0-71f7-41b9-b068-579183645fba
caps.latest.revision: 9
manager: ghogen
translationtype: Machine Translation
ms.sourcegitcommit: 85c900f2263ae1c1089478badc85388e3b5e8548
ms.openlocfilehash: 6c11e1f90ce05aa3a4dc22ce31bed104ef0fa795
ms.lasthandoff: 02/24/2017

---
# <a name="lthashmapgt-functions"></a>&lt;hash_map&gt; 関数
|||  
|-|-|  
|[swap](#swap)|[swap (hash_map)](#swap__hash_map_)|  
  
##  <a name="a-nameswaphashmapa--swap-hashmap"></a><a name="swap__hash_map_"></a>  swap (hash_map)  
  
> [!NOTE]
>  この API は、互換性のために残されています。 代わりに、[unordered_map クラス](../standard-library/unordered-map-class.md)を使用してください。  
  
 2 つの hash_map の要素を交換します。  
  
```
void swap(
    hash_map <Key, Type, Traits, Alloctor>& left,
    hash_map <Key, Type, Traits, Allocator>& right);
```  
  
### <a name="parameters"></a>パラメーター  
 `right`  
 要素が map `left` の要素と交換される hash_map。  
  
 `left`  
 要素が map `right` の要素と交換される hash_map。  
  
### <a name="remarks"></a>コメント  
 テンプレート関数は、コンテナー クラス hash_map に特化したアルゴリズムであり、メンバー関数 `left.`[swap](../standard-library/basic-ios-class.md#basic_ios__swap)*(right*) を実行します。 これは、コンパイラによる関数テンプレートの部分的な順序付けのインスタンスです。 テンプレートと関数呼び出しの照合が一意にならないようにテンプレート関数がオーバーロードされた場合、コンパイラは、最も特化したバージョンのテンプレート関数を選択します。 テンプレート関数の一般的なバージョンであり、algorithm ヘッダー ファイルにある **template \<class T> void swap(T&, T&)** は、代入によって機能し、処理が低速です。 各コンテナー内の特化バージョンのほうが、コンテナー クラスの内部表現で使用できるため大幅に高速になります。  
  
 Visual C++ .NET 2003 では、[<hash_map>](../standard-library/hash-map.md) ヘッダー ファイルと [<hash_set>](../standard-library/hash-set.md) ヘッダー ファイルのメンバーは、std 名前空間に存在しなくなりましたが、stdext 名前空間に移動されました。 詳細については、「[The stdext 名前空間](../standard-library/stdext-namespace.md)」をご覧ください。  
  
##  <a name="a-nameswapa--swap"></a><a name="swap"></a>  swap  
  
> [!NOTE]
>  この API は、互換性のために残されています。 代替が必要な場合は、[unordered_multimap クラス](../standard-library/unordered-multimap-class.md)をご使用ください。  
  
 2 つの hash_multimap の要素を交換します。  
  
```
void swap(
    hash_multimap <Key, Type, Traits, Alloctor>& left,
    hash_multimap <Key, Type, Traits, Allocator>& right);
```  
  
### <a name="parameters"></a>パラメーター  
 `right`  
 要素が map `left` の要素と交換される hash_multimap。  
  
 `left`  
 要素が map `right` の要素と交換される hash_multimap。  
  
### <a name="remarks"></a>コメント  
 テンプレート関数は、コンテナー クラス hash_multimap に特化したアルゴリズムであり、メンバー関数 `left.`[swap](../standard-library/hash-multimap-class.md#hash_multimap__swap)*(right*`)` を実行します。 これは、コンパイラによる関数テンプレートの部分的な順序付けのインスタンスです。 テンプレートと関数呼び出しの照合が一意にならないようにテンプレート関数がオーバーロードされた場合、コンパイラは、最も特化したバージョンのテンプレート関数を選択します。 テンプレート関数の一般的なバージョンであり、algorithm ヘッダー ファイルにある **template \<class T> void swap(T&, T&)** は、代入によって機能し、処理が低速です。 各コンテナー内の特化バージョンのほうが、コンテナー クラスの内部表現で使用できるため大幅に高速になります。  
  
 Visual C++ .NET 2003 では、[<hash_map>](../standard-library/hash-map.md) ヘッダー ファイルと [<hash_set>](../standard-library/hash-set.md) ヘッダー ファイルのメンバーは、std 名前空間に存在しなくなりましたが、stdext 名前空間に移動されました。 詳細については、「[The stdext 名前空間](../standard-library/stdext-namespace.md)」をご覧ください。  
  
## <a name="see-also"></a>関連項目  
 [<hash_map>](../standard-library/hash-map.md)




