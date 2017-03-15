---
title: "&lt;map&gt; 系関数 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 7cb3d1a5-7add-4726-a73f-61927eafd466
caps.latest.revision: 6
manager: ghogen
translationtype: Machine Translation
ms.sourcegitcommit: 85c900f2263ae1c1089478badc85388e3b5e8548
ms.openlocfilehash: d322b318ac4206c5bc27b81299190d129548ef9f
ms.lasthandoff: 02/24/2017

---
# <a name="ltmapgt-functions"></a>&lt;map&gt; 系関数
|||  
|-|-|  
|[swap (map)](#swap)|[swap (multimap)](#swap_multimap)|  
  
##  <a name="a-nameswapmultimapa--swap--map"></a><a name="swap_multimap"></a>  swap  (map)
 2 つの map の要素を交換します。  
  
```  
template <class key, class T, class _Pr, class _Alloc>  
void swap(
    map<Key, Traits, Compare, Alloctor>& left,  
    map<Key, Traits, Compare, Alloctor>& right);
```  
  
### <a name="parameters"></a>パラメーター  
 ` right`  
 交換する要素を提供する map (map ` left` と要素を交換する map)。  
  
 ` left`  
 要素が map ` right` の要素と交換される map。  
  
### <a name="remarks"></a>コメント  
 テンプレート関数は、コンテナー クラス map に特化したアルゴリズムであり、メンバー関数 ` left.`[swap](../standard-library/map-class.md#map__swap)*(right*) を実行します。 これは、コンパイラによる関数テンプレートの部分的な順序付けのインスタンスです。 テンプレートと関数呼び出しの照合が一意にならないようにテンプレート関数がオーバーロードされた場合、コンパイラは、最も特化したバージョンのテンプレート関数を選択します。 テンプレート関数の一般的なバージョンであり、algorithm クラスにある **template** \< **class T**> **void swap**(**T&**, **T&**) は、代入によって機能し、処理が低速です。 各コンテナー内の特化バージョンのほうが、コンテナー クラスの内部表現で使用できるため大幅に高速になります。  
  
### <a name="example"></a>例  
  `swap` のテンプレート バージョンの使用例については、メンバー関数 [map::swap](../standard-library/map-class.md#map__swap) のコード例をご覧ください。  
  
##  <a name="a-nameswapa--swap--multimap"></a><a name="swap"></a>  swap  (multimap)
 2 つの multimap の要素を交換します。  
  
```  
template <class key, class T, class _Pr, class _Alloc>  
void swap(
    multimap<Key, Traits, Compare, Alloctor>& left,  
    multimap<Key, Traits, Compare, Alloctor>& right);
```  
  
### <a name="parameters"></a>パラメーター  
 ` right`  
 交換する要素を提供する multimap (multimap ` left` と要素を交換する multimap)。  
  
 ` left`  
 要素が multimap ` right` の要素と交換される multimap。  
  
### <a name="remarks"></a>コメント  
 テンプレート関数は、コンテナー クラス multimap に特化したアルゴリズムであり、メンバー関数 ` left.`[swap](../standard-library/multimap-class.md#multimap__swap) (` right`) を実行します。 これは、コンパイラによる関数テンプレートの部分的な順序付けのインスタンスです。 テンプレートと関数呼び出しの照合が一意にならないようにテンプレート関数がオーバーロードされた場合、コンパイラは、最も特化したバージョンのテンプレート関数を選択します。 テンプレート関数の一般的なバージョンであり、algorithm クラスにある **template** \< **class T**> **void swap**(**T&**, **T&**) は、代入によって機能し、処理が低速です。 各コンテナー内の特化バージョンのほうが、コンテナー クラスの内部表現で使用できるため大幅に高速になります。  
  
### <a name="example"></a>例  
  `swap` のテンプレート バージョンの使用例については、メンバー関数 [multimap::swap](../standard-library/multimap-class.md#multimap__swap) のコード例をご覧ください。  
  
## <a name="see-also"></a>関連項目  
 [\<map>](../standard-library/map.md)

