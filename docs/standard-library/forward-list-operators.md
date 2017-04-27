---
title: "&lt;forward_list&gt; 演算子 | Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: []
ms.assetid: 57492e09-3836-4dbc-9ae5-78ecf506c190
caps.latest.revision: 11
manager: ghogen
translationtype: Machine Translation
ms.sourcegitcommit: 3168772cbb7e8127523bc2fc2da5cc9b4f59beb8
ms.openlocfilehash: a560de0a7587b5552fc663bdd2b44734a66b5f73
ms.lasthandoff: 02/24/2017

---
# <a name="ltforwardlistgt-operators"></a>&lt;forward_list&gt; 演算子
||||  
|-|-|-|  
|[operator!=](#operator_neq)|[operator&gt;](#operator_gt_)|[operator&gt;=](#operator_gt__eq)|  
|[operator&lt;](#operator_lt_)|[operator&lt;=](#operator_lt__eq)|[operator==](#operator_eq_eq)|  
  
##  <a name="operator_eq_eq"></a>  operator==  
 演算子の左辺の前方リスト オブジェクトが右辺の前方リスト オブジェクトと等しいかどうかを調べます。  
  
```
bool operator==(
    const forward_list <Type, Allocator>& left,
    const forward_list <Type, Allocator>& right);
```  
  
### <a name="parameters"></a>パラメーター  
  
|パラメーター|説明|  
|---------------|-----------------|  
|`left`|`forward_list` 型のオブジェクト。|  
|`right`|`forward_list` 型のオブジェクト。|  
  
### <a name="remarks"></a>コメント  
 このテンプレート関数は、テンプレート クラス `forward_list` の&2; つのオブジェクトを比較する `operator==` をオーバーロードします。 `distance(left.begin(), end()) == distance(right.begin(),right.end()) && equal(left. begin(),left. end(),right.begin())` が返されます。  
  
##  <a name="operator_neq"></a>  operator!=  
 演算子の左辺の前方リスト オブジェクトが右辺の前方リスト オブジェクトと等しくないかどうかを調べます。  
  
```
bool operator!=(
    const forward_list <Type, Allocator>& left,
    const forward_list <Type, Allocator>& right);
```  
  
### <a name="parameters"></a>パラメーター  
  
|パラメーター|説明|  
|---------------|-----------------|  
|`left`|`forward_list` 型のオブジェクト。|  
|`right`|`forward_list` 型のオブジェクト。|  
  
### <a name="return-value"></a>戻り値  
 リストが等しくない場合は **true**、リストが等しい場合は **false**。  
  
### <a name="remarks"></a>コメント  
 このテンプレート関数は `!(left == right)` を返します。  
  
##  <a name="operator_lt_"></a>  operator&lt;  
 演算子の左辺の前方リスト オブジェクトが右辺の前方リスト オブジェクトより小さいかどうかを調べます。  
  
```
bool operator<(
    const forward_list <Type, Allocator>& left,
    const forward_list <Type, Allocator>& right);
```  
  
### <a name="parameters"></a>パラメーター  
  
|パラメーター|説明|  
|---------------|-----------------|  
|`left`|`forward_list` 型のオブジェクト。|  
|`right`|`forward_list` 型のオブジェクト。|  
  
### <a name="return-value"></a>戻り値  
 演算子の左辺のリストが演算子の右辺のリストより小さい場合は `true`、それ以外の場合は `false`。  
  
### <a name="remarks"></a>コメント  
 このテンプレート関数は、テンプレート クラス `forward_list` の&2; つのオブジェクトを比較する `operator<` をオーバーロードします。 `lexicographical_compare(lhs. begin(), lhs. end(), rhs.begin(), rhs.end())` が返されます。  
  
##  <a name="operator_lt__eq"></a>  operator&lt;=  
 演算子の左辺の前方リスト オブジェクトが右辺の前方リスト オブジェクト以下であるかどうかを調べます。  
  
```
bool operator<=(
    const forward_list <Type, Allocator>& left,
    const forward_list <Type, Allocator>& right);
```  
  
### <a name="parameters"></a>パラメーター  
  
|パラメーター|説明|  
|---------------|-----------------|  
|`left`|`forward_list` 型のオブジェクト。|  
|`right`|`forward_list` 型のオブジェクト。|  
  
### <a name="return-value"></a>戻り値  
 演算子の左辺のリストが演算子の右辺のリスト以下である場合は `true`、それ以外の場合は `false`。  
  
### <a name="remarks"></a>コメント  
 このテンプレート関数は `!(right < left)` を返します。  
  
##  <a name="operator_gt_"></a>  operator&gt;  
 演算子の左辺の前方リスト オブジェクトが右辺の前方リスト オブジェクトより大きいかどうかを調べます。  
  
```
bool operator>(
    const forward_list <Type, Allocator>& left,
    const forward_list <Type, Allocator>& right);
```  
  
### <a name="parameters"></a>パラメーター  
  
|パラメーター|説明|  
|---------------|-----------------|  
|`left`|`forward_list` 型のオブジェクト。|  
|`right`|`forward_list` 型のオブジェクト。|  
  
### <a name="return-value"></a>戻り値  
 演算子の左辺のリストが演算子の右辺のリストより大きい場合は `true`、それ以外の場合は `false`。  
  
### <a name="remarks"></a>コメント  
 このテンプレート関数は `right < left` を返します。  
  
##  <a name="operator_gt__eq"></a>  operator&gt;=  
 演算子の左辺の前方リスト オブジェクトが右辺の前方リスト オブジェクト以上であるかどうかを調べます。  
  
```
bool operator>=(
    const forward_list <Type, Allocator>& left,
    const forward_list <Type, Allocator>& right);
```  
  
### <a name="parameters"></a>パラメーター  
  
|パラメーター|説明|  
|---------------|-----------------|  
|`left`|`forward_list` 型のオブジェクト。|  
|`right`|`forward_list` 型のオブジェクト。|  
  
### <a name="return-value"></a>戻り値  
 演算子の左辺の前方リストが演算子の右辺の前方リスト以上である場合は `true`、それ以外の場合は `false`。  
  
### <a name="remarks"></a>コメント  
 このテンプレート関数は `!(left < right)` を返します。  
  
## <a name="see-also"></a>関連項目  
 [<forward_list>](../standard-library/forward-list.md)




