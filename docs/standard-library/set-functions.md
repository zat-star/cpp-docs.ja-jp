---
title: "&lt;set&gt; 系関数 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- set/std::swap (map)
- set/std::swap (multiset)
ms.assetid: d1277d14-8502-46c0-b820-bcda820f9406
caps.latest.revision: 7
manager: ghogen
ms.translationtype: Machine Translation
ms.sourcegitcommit: 66798adc96121837b4ac2dd238b9887d3c5b7eef
ms.openlocfilehash: 6c26128064b2f20a55ab1b9d1c013829e72523e0
ms.contentlocale: ja-jp
ms.lasthandoff: 04/29/2017

---
# <a name="ltsetgt-functions"></a>&lt;set&gt; 系関数
|||  
|-|-|  
|[swap (map)](#swap)|[swap (multiset)](#swap_multiset)|  
  
##  <a name="swap"></a>  swap  (map)
 2 つの set の要素を交換します。  
  
```
template <class Key, class Traits, class Allocator>  
void swap(set<Key, Traits, Allocator>& left, set<Key, Traits, Allocator>& right);
```  
  
### <a name="parameters"></a>パラメーター  
 `right`  
 交換する要素を提供する set (set `left` と要素を交換する set)。  
  
 `left`  
 要素が set `right` の要素と交換される set。  
  
### <a name="remarks"></a>コメント  
 テンプレート関数は、コンテナー クラス set に特化したアルゴリズムであり、メンバー関数 `left``.`[swap](../standard-library/set-class.md#swap)(`right`) を実行します。 これは、コンパイラによる関数テンプレートの部分的な順序付けのインスタンスです。 テンプレートと関数呼び出しの照合が一意にならないようにテンプレート関数がオーバーロードされた場合、コンパイラは、最も特化したバージョンのテンプレート関数を選択します。 テンプレート関数の一般的なバージョン  
  
 `template` \< **classT**> **void swap**( **T&**, **T&**)  
  
 は、algorithm クラスにあり、代入によって機能し、処理は低速です。 各コンテナー内の特化バージョンのほうが、コンテナー クラスの内部表現で使用できるため大幅に高速になります。  
  
### <a name="example"></a>例  
  `swap` のテンプレート バージョンの使用例については、メンバー クラス [set::swap](../standard-library/set-class.md#swap) のコード例をご覧ください。  
  
##  <a name="swap_multiset"></a>  swap  (multiset)
 2 つの multiset の要素を交換します。  
  
```
template <class Key, class Traits, class Allocator>  
void swap(multiset<Key, Traits, Allocator>& left, multiset<Key, Traits, Allocator>& right);
```  
  
### <a name="parameters"></a>パラメーター  
 `right`  
 交換する要素を提供する multiset (multiset `left` と要素を交換する multiset)。  
  
 `left`  
 要素が multiset `right` の要素と交換される multiset。  
  
### <a name="remarks"></a>コメント  
 テンプレート関数は、コンテナー クラス multiset に特化したアルゴリズムであり、メンバー関数 `left``.`[swap](../standard-library/multiset-class.md#swap)(`right`) を実行します。 これは、コンパイラによる関数テンプレートの部分的な順序付けのインスタンスです。 テンプレートと関数呼び出しの照合が一意にならないようにテンプレート関数がオーバーロードされた場合、コンパイラは、最も特化したバージョンのテンプレート関数を選択します。 テンプレート関数の一般的なバージョン  
  
 `template` \< **classT**> **void swap**( **T&**, **T&**)  
  
 は、algorithm クラスにあり、代入によって機能し、処理は低速です。 各コンテナー内の特化バージョンのほうが、コンテナー クラスの内部表現で使用できるため大幅に高速になります。  
  
### <a name="example"></a>例  
  `swap` のテンプレート バージョンの使用例については、メンバー クラス [multiset::swap](../standard-library/multiset-class.md#swap) のコード例をご覧ください。  
  
## <a name="see-also"></a>関連項目  
 [\<set>](../standard-library/set.md)




