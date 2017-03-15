---
title: "&lt;thread&gt; 演算子 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e6bb6c0f-64f9-4cb2-9ff2-05b88a6ba7ac
caps.latest.revision: 11
manager: ghogen
translationtype: Machine Translation
ms.sourcegitcommit: a937c9d083a7e4331af63323a19fb207142604a0
ms.openlocfilehash: 7e849e8585b372b5b423a6c960aa926ac7d5cfec
ms.lasthandoff: 02/24/2017

---
# <a name="ltthreadgt-operators"></a>&lt;thread&gt; 演算子
||||  
|-|-|-|  
|[operator!=](#operator_neq)|[operator&gt;](#operator_gt_)|[operator&gt;=](#operator_gt__eq)|  
|[operator&lt;](#operator_lt_)|[operator&lt;&lt;](#operator_lt__lt_)|[operator&lt;=](#operator_lt__eq)|  
|[operator==](#operator_eq_eq)|  
  
##  <a name="a-nameoperatorgteqa--operatorgt"></a><a name="operator_gt__eq"></a>  operator&gt;=  
 一方の `thread::id` オブジェクトの値が、もう一方のオブジェクトの値以上かどうかを判断します。  
  
```cpp  
bool operator>= (
    thread::id Left,
    thread::id Right) noexcept
```  
  
### <a name="parameters"></a>パラメーター  
 `Left`  
 左側の `thread::id` オブジェクト。  
  
 `Right`  
 右側の `thread::id` オブジェクト。  
  
### <a name="return-value"></a>戻り値  
 `!(Left < Right)`  
  
### <a name="remarks"></a>コメント  
 この関数では、例外がスローされません。  
  
##  <a name="a-nameoperatorgta--operatorgt"></a><a name="operator_gt_"></a>  operator&gt;  
 一方の `thread::id` オブジェクトの値が、もう一方のオブジェクトの値より大きいかどうかを判断します。  
  
```cpp  
bool operator> (
    thread::id Left,
    thread::id Right) noexcept
```  
  
### <a name="parameters"></a>パラメーター  
 `Left`  
 左側の `thread::id` オブジェクト。  
  
 `Right`  
 右側の `thread::id` オブジェクト。  
  
### <a name="return-value"></a>戻り値  
 `Right < Left`  
  
### <a name="remarks"></a>コメント  
 この関数では、例外がスローされません。  
  
##  <a name="a-nameoperatorlteqa--operatorlt"></a><a name="operator_lt__eq"></a>  operator&lt;=  
 一方の `thread::id` オブジェクトの値が、もう一方のオブジェクトの値以下かどうかを判断します。  
  
```cpp  
bool operator<= (
    thread::id Left,
    thread::id Right) noexcept
```  
  
### <a name="parameters"></a>パラメーター  
 `Left`  
 左側の `thread::id` オブジェクト。  
  
 `Right`  
 右側の `thread::id` オブジェクト。  
  
### <a name="return-value"></a>戻り値  
 `!(Right < Left)`  
  
### <a name="remarks"></a>コメント  
 この関数では、例外がスローされません。  
  
##  <a name="a-nameoperatorlta--operatorlt"></a><a name="operator_lt_"></a>  operator&lt;  
 一方の `thread::id` オブジェクトの値が、もう一方のオブジェクトの値より小さいかどうかを判断します。  
  
```cpp  
bool operator<(
    thread::id Left,
    thread::id Right) noexcept
```  
  
### <a name="parameters"></a>パラメーター  
 `Left`  
 左側の `thread::id` オブジェクト。  
  
 `Right`  
 右側の `thread::id` オブジェクト。  
  
### <a name="return-value"></a>戻り値  
 全体の順序付けの中で `Left` が `Right` よりも前にある場合は `true`、それ以外の場合は `false`。  
  
### <a name="remarks"></a>コメント  
 この演算子は、すべての `thread::id` オブジェクトでの全体の順序付けを定義します。 これらのオブジェクトは、連想コンテナー内のキーとして使用できます。  
  
 この関数では、例外がスローされません。  
  
##  <a name="a-nameoperatorneqa--operator"></a><a name="operator_neq"></a>  operator!=  
 2 つの `thread::id` オブジェクトが等しくないかどうかを比較します。  
  
```cpp  
bool operator!= (
    thread::id Left,
    thread::id Right) noexcept
```  
  
### <a name="parameters"></a>パラメーター  
 `Left`  
 左側の `thread::id` オブジェクト。  
  
 `Right`  
 右側の `thread::id` オブジェクト。  
  
### <a name="return-value"></a>戻り値  
 `!(Left == Right)`  
  
### <a name="remarks"></a>コメント  
 この関数では、例外がスローされません。  
  
##  <a name="a-nameoperatoreqeqa--operator"></a><a name="operator_eq_eq"></a>  operator==  
 2 つの `thread::id` オブジェクトが等しいかどうかを比較します。  
  
```cpp  
bool operator== (
    thread::id Left,
    thread::id Right) noexcept
```  
  
### <a name="parameters"></a>パラメーター  
 `Left`  
 左側の `thread::id` オブジェクト。  
  
 `Right`  
 右側の `thread::id` オブジェクト。  
  
### <a name="return-value"></a>戻り値  
 2 つのオブジェクトが同じ実行スレッドを表している場合、またはいずれのオブジェクトも実行スレッドを表していない場合は `true`、それ以外の場合は `false`。  
  
### <a name="remarks"></a>コメント  
 この関数では、例外がスローされません。  
  
##  <a name="a-nameoperatorltlta--operatorltlt"></a><a name="operator_lt__lt_"></a>  operator&lt;&lt;  
 `thread::id` オブジェクトのテキスト表現をストリームに挿入します。  
  
```cpp  
template <class Elem, class Tr>
basic_ostream<Elem, Tr>& operator<<(
    basic_ostream<Elem, Tr>& Ostr, thread::id Id);
```  
  
### <a name="parameters"></a>パラメーター  
 `Ostr`  
 [basic_ostream](../standard-library/basic-ostream-class.md) オブジェクト。  
  
 `Id`  
 `thread::id` オブジェクト。  
  
### <a name="return-value"></a>戻り値  
 `Ostr`。  
  
### <a name="remarks"></a>コメント  
 この関数は、`Ostr` に `Id` を挿入します。  
  
 2 つの `thread::id` オブジェクトが等しい場合、これらのオブジェクトの挿入されたテキスト表現は同じです。  
  
## <a name="see-also"></a>関連項目  
 [\<thread>](../standard-library/thread.md)




