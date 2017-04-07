---
title: "concurrency 名前空間演算子 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- concrt/concurrency::operator!=
- concrt/concurrency:[operator&amp;&amp
- concrt/concurrency:[operator&amp;&amp
dev_langs:
- C++
ms.assetid: 8e373f23-fc8e-49f7-82e6-ba0c57b822f8
caps.latest.revision: 7
author: mikeblome
ms.author: mblome
manager: ghogen
translationtype: Machine Translation
ms.sourcegitcommit: 5faef5bd1be6cc02d6614a6f6193c74167a8ff23
ms.openlocfilehash: 322c95da1774cb0b1d621a46c74125f435ebfbc4
ms.lasthandoff: 03/17/2017

---
# <a name="concurrency-namespace-operators"></a>concurrency 名前空間演算子
||||  
|-|-|-|  
|[operator!=](#operator_neq)|[operator&amp;&amp;](#operator_amp_amp)|[operator&gt;](#operator_gt)|  
|[operator&gt;=](#operator_gt_eq)|[operator&lt;](#operator_lt)|[operator&lt;=](#operator_lt_eq)|  
|[operator==](#operator_eq_eq)|[operator||](#operator_lor)|  
  
##  <a name="operator_lor"></a>operator | |演算子  
 引数として指定されたいずれかのタスクが正常に完了したときに正常に完了するタスクを作成します。  
  
```  
template<typename ReturnType>  
task<ReturnType> operator||(
    const task<ReturnType>& lhs,  
    const task<ReturnType>& rhs);

 
template<typename ReturnType>  
task<std::vector<ReturnType>> operator||(
    const task<std::vector<ReturnType>>& lhs,  
    const task<ReturnType>& rhs);

 
template<typename ReturnType>  
task<std::vector<ReturnType>> operator||(
    const task<ReturnType>& lhs,  
    const task<std::vector<ReturnType>>& rhs);

 
inline task<void> operator||(
    const task<void>& lhs,  
    const task<void>& rhs);
```  
  
### <a name="parameters"></a>パラメーター  
 `ReturnType`  
 返されるタスクの種類。  
  
 `lhs`  
 結果のタスクにまとめられる最初のタスク。  
  
 `rhs`  
 結果のタスクにまとめられる&2; 番目のタスク。  
  
### <a name="return-value"></a>戻り値  
 入力したタスクのいずれかが正常に完了したときのタスクです。 入力したタスクの種類が `T` である場合、この関数の出力は `task<std::vector<T>` になります。 入力したタスクの種類が `void` である場合、出力のタスクも `task<void>` になります。  
  
### <a name="remarks"></a>コメント  
 両方のタスクが取り消されたまたは例外をスローする、取り消された状態に戻されるタスクは完了し、例外のいずれかが発生した場合がスローされますを呼び出したときに`get()`または`wait()`タスクにします。  
  
##  <a name="operator_amp_amp"></a>演算子&amp;&amp;演算子  
 引数として指定された両方のタスクが正常に完了したときに正常に完了するタスクを作成します。  
  
```  
template<typename ReturnType>  
task<std::vector<ReturnType>>  operator&&(
    const task<ReturnType>& lhs,  
    const task<ReturnType>& rhs);

 
template<typename ReturnType>  
task<std::vector<ReturnType>>  operator&&(
    const task<std::vector<ReturnType>>& lhs,  
    const task<ReturnType>& rhs);

 
template<typename ReturnType>  
task<std::vector<ReturnType>>  operator&&(
    const task<ReturnType>& lhs,  
    const task<std::vector<ReturnType>>& rhs);

 
template<typename ReturnType>  
task<std::vector<ReturnType>>  operator&&(
    const task<std::vector<ReturnType>>& lhs,  
    const task<std::vector<ReturnType>>& rhs);

 
inline task<void>  operator&&(
    const task<void>& lhs,  
    const task<void>& rhs);
```  
  
### <a name="parameters"></a>パラメーター  
 `ReturnType`  
 返されるタスクの種類。  
  
 `lhs`  
 結果のタスクにまとめられる最初のタスク。  
  
 `rhs`  
 結果のタスクにまとめられる&2; 番目のタスク。  
  
### <a name="return-value"></a>戻り値  
 入力した両方のタスクが正常に完了したときに正常に完了するタスク。 入力したタスクの種類が `T` である場合、この関数の出力は `task<std::vector<T>>` になります。 入力したタスクの種類が `void` である場合、出力のタスクも `task<void>` になります。  
  
### <a name="remarks"></a>コメント  
 タスクのどちらか&1; つが取り消された場合、または例外をスローした場合、返されるタスクは早期に完了し、取り消された状態になります。また例外が発生したときは、そのタスクに対して `get()` または `wait()` を呼び出す場合に、その例外がスローされます。  
  
##  <a name="operator_eq_eq"></a>operator = 演算子  
 演算子の左側の `concurrent_vector` オブジェクトが右側の `concurrent_vector` オブジェクトと等しいかどうかを調べます。  
  
```  
template<typename T, class A1, class A2>  
inline bool operator== (
    const concurrent_vector<T, A1>& _A,  
    const concurrent_vector<T, A2>& _B);
```  
  
### <a name="parameters"></a>パラメーター  
 `T`  
 同時実行ベクターに格納された要素のデータ型。  
  
 `A1`  
 1 つ目のアロケーターの型`concurrent_vector`オブジェクトです。  
  
 `A2`  
 2 つ目のアロケーターの型`concurrent_vector`オブジェクトです。  
  
 `_A`  
 `concurrent_vector` 型のオブジェクト。  
  
 `_B`  
 `concurrent_vector` 型のオブジェクト。  
  
### <a name="return-value"></a>戻り値  
 `true`演算子の左側にある同時実行ベクターが演算子の右側にある同時実行ベクターに等しい場合それ以外の場合`false`します。  
  
### <a name="remarks"></a>コメント  
 2 つの同時実行ベクターは、同じ数の要素を持ち、対応する要素があると同じ値です。 それ以外の場合は等しくありません。  
  
 このメソッドは同時実行ベクターのいずれかの変更が他のメソッドは同時実行セーフではありません`_A`または`_B`です。  
  
##  <a name="operator_neq"></a>operator! = 演算子  
 演算子の左側の `concurrent_vector` オブジェクトが右側の `concurrent_vector` オブジェクトと等しくないかどうかを調べます。  
  
```  
template<typename T, class A1, class A2>  
inline bool operator!= (
    const concurrent_vector<T, A1>& _A,  
    const concurrent_vector<T, A2>& _B);
```  
  
### <a name="parameters"></a>パラメーター  
 `T`  
 同時実行ベクターに格納された要素のデータ型。  
  
 `A1`  
 1 つ目のアロケーターの型`concurrent_vector`オブジェクトです。  
  
 `A2`  
 2 つ目のアロケーターの型`concurrent_vector`オブジェクトです。  
  
 `_A`  
 `concurrent_vector` 型のオブジェクト。  
  
 `_B`  
 `concurrent_vector` 型のオブジェクト。  
  
### <a name="return-value"></a>戻り値  
 `true`同時実行ベクターが等しくない場合`false`同時実行ベクターが等しい場合。  
  
### <a name="remarks"></a>コメント  
 2 つの同時実行ベクターは、同じ数の要素を持ち、対応する要素があると同じ値です。 それ以外の場合は等しくありません。  
  
 このメソッドは同時実行ベクターのいずれかの変更が他のメソッドは同時実行セーフではありません`_A`または`_B`です。  
  
##  <a name="operator_lt"></a>演算子&lt;演算子  
 演算子の左側の `concurrent_vector` オブジェクトが右側の `concurrent_vector` オブジェクトより小さいかどうかを調べます。  
  
```  
template<typename T, class A1, class A2>  
inline bool operator<(
    const concurrent_vector<T, A1>& _A,  
    const concurrent_vector<T, A2>& _B);
```  
  
### <a name="parameters"></a>パラメーター  
 `T`  
 同時実行ベクターに格納された要素のデータ型。  
  
 `A1`  
 1 つ目のアロケーターの型`concurrent_vector`オブジェクトです。  
  
 `A2`  
 2 つ目のアロケーターの型`concurrent_vector`オブジェクトです。  
  
 `_A`  
 `concurrent_vector` 型のオブジェクト。  
  
 `_B`  
 `concurrent_vector` 型のオブジェクト。  
  
### <a name="return-value"></a>戻り値  
 `true`演算子の左側にある同時実行ベクターが演算子の右側にある同時実行ベクターより小さい場合それ以外の場合`false`します。  
  
### <a name="remarks"></a>コメント  
 この演算子の動作に相当する演算子のと同じ、`vector`クラス、`std`名前空間。  
  
 このメソッドは同時実行ベクターのいずれかの変更が他のメソッドは同時実行セーフではありません`_A`または`_B`です。  
  
##  <a name="operator_lt_eq"></a>演算子&lt;= 演算子  
 演算子の左側の `concurrent_vector` オブジェクトが右側の  `concurrent_vector` オブジェクト以下かどうかを調べます。  
  
```  
template<typename T, class A1, class A2>  
inline bool operator<= (
    const concurrent_vector<T, A1>& _A,  
    const concurrent_vector<T, A2>& _B);
```  
  
### <a name="parameters"></a>パラメーター  
 `T`  
 同時実行ベクターに格納された要素のデータ型。  
  
 `A1`  
 1 つ目のアロケーターの型`concurrent_vector`オブジェクトです。  
  
 `A2`  
 2 つ目のアロケーターの型`concurrent_vector`オブジェクトです。  
  
 `_A`  
 `concurrent_vector` 型のオブジェクト。  
  
 `_B`  
 `concurrent_vector` 型のオブジェクト。  
  
### <a name="return-value"></a>戻り値  
 `true`演算子の左側にある同時実行ベクターが演算子の右側にある同時実行ベクター以下である場合それ以外の場合`false`します。  
  
### <a name="remarks"></a>コメント  
 この演算子の動作に相当する演算子のと同じ、`vector`クラス、`std`名前空間。  
  
 このメソッドは同時実行ベクターのいずれかの変更が他のメソッドは同時実行セーフではありません`_A`または`_B`です。  
  
##  <a name="operator_gt"></a>演算子&gt;演算子  
 演算子の左側の `concurrent_vector` オブジェクトが右側の `concurrent_vector` オブジェクトより大きいかどうかを調べます。  
  
```  
template<typename T, class A1, class A2>  
inline bool operator>(
    const concurrent_vector<T, A1>& _A,  
    const concurrent_vector<T, A2>& _B);
```  
  
### <a name="parameters"></a>パラメーター  
 `T`  
 同時実行ベクターに格納された要素のデータ型。  
  
 `A1`  
 1 つ目のアロケーターの型`concurrent_vector`オブジェクトです。  
  
 `A2`  
 2 つ目のアロケーターの型`concurrent_vector`オブジェクトです。  
  
 `_A`  
 `concurrent_vector` 型のオブジェクト。  
  
 `_B`  
 `concurrent_vector` 型のオブジェクト。  
  
### <a name="return-value"></a>戻り値  
 `true`演算子の左側にある同時実行ベクターが演算子の右側にある同時実行ベクターを超える場合それ以外の場合`false`します。  
  
### <a name="remarks"></a>コメント  
 この演算子の動作に相当する演算子のと同じ、`vector`クラス、`std`名前空間。  
  
 このメソッドは同時実行ベクターのいずれかの変更が他のメソッドは同時実行セーフではありません`_A`または`_B`です。  
  
##  <a name="operator_gt_eq"></a>演算子&gt;= 演算子  
 演算子の左側の `concurrent_vector` オブジェクトが右側の `concurrent_vector` オブジェクト以上であるかどうかを調べます。  
  
```  
template<typename T, class A1, class A2>  
inline bool operator>= (
    const concurrent_vector<T, A1>& _A,  
    const concurrent_vector<T, A2>& _B);
```  
  
### <a name="parameters"></a>パラメーター  
 `T`  
 同時実行ベクターに格納された要素のデータ型。  
  
 `A1`  
 1 つ目のアロケーターの型`concurrent_vector`オブジェクトです。  
  
 `A2`  
 2 つ目のアロケーターの型`concurrent_vector`オブジェクトです。  
  
 `_A`  
 `concurrent_vector` 型のオブジェクト。  
  
 `_B`  
 `concurrent_vector` 型のオブジェクト。  
  
### <a name="return-value"></a>戻り値  
 `true`演算子の左側にある同時実行ベクターが演算子の右側にある同時実行ベクター以上である場合それ以外の場合`false`します。  
  
### <a name="remarks"></a>コメント  
 この演算子の動作に相当する演算子のと同じ、`vector`クラス、`std`名前空間。  
  
 このメソッドは同時実行ベクターのいずれかの変更が他のメソッドは同時実行セーフではありません`_A`または`_B`です。  
  
## <a name="see-also"></a>関連項目  
 [concurrency 名前空間](concurrency-namespace.md)

