---
title: "combinable クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- combinable
- PPL/concurrency::combinable
- PPL/concurrency::combinable::combinable
- PPL/concurrency::combinable::clear
- PPL/concurrency::combinable::combine
- PPL/concurrency::combinable::combine_each
- PPL/concurrency::combinable::local
dev_langs:
- C++
helpviewer_keywords:
- combinable class
ms.assetid: fe0bfbf6-6250-47da-b8d0-f75369f0b5be
caps.latest.revision: 20
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
translationtype: Machine Translation
ms.sourcegitcommit: 5faef5bd1be6cc02d6614a6f6193c74167a8ff23
ms.openlocfilehash: a491f8eef59978808608917531a5237cceacdb21
ms.lasthandoff: 03/17/2017

---
# <a name="combinable-class"></a>combinable クラス
`combinable<T>` オブジェクトは、スレッド プライベートなデータのコピーを提供し、並列アルゴリズムにおいてロック制御不要なスレッド ローカルのサブ計算を実行するために用意されています。 並列操作の最後に、スレッド プライベート サブ計算を最終結果に結合できます。 共有変数に多数の競合が発生する可能性がある場合、共有変数の代わりにこのクラスを使用することにより、パフォーマンスを改善できます。  
  
## <a name="syntax"></a>構文  
  
```
template<typename T>
class combinable;
```  
  
#### <a name="parameters"></a>パラメーター  
 `T`  
 最終的なマージされた結果のデータ型。 種類は、コピー コンス トラクターと既定のコンス トラクターが必要です。  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[組み合わせ可能](#ctor)|オーバーロードされます。 新しい `combinable` オブジェクトを構築します。|  
|[~ combinable デストラクター](#dtor)|`combinable` オブジェクトを破棄します。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[clear](#clear)|以前の使用法から中間の計算結果をクリアします。|  
|[combine](#combine)|指定された結合ファンクタを呼び出すことによって、スレッド ローカルのサブ計算のセットから最終的な値を計算します。|  
|[combine_each](#combine_each)|スレッド ローカルのサブ計算ごとに&1; 回、指定された結合ファンクタを呼び出すことによって、スレッド ローカルのサブ計算のセットから最終的な値を計算します。 最終的な結果は、関数オブジェクトによっては累積されます。|  
|[地元の](#local)|オーバーロードされます。 スレッド プライベート サブ計算への参照を返します。|  
  
### <a name="public-operators"></a>パブリック演算子  
  
|名前|説明|  
|----------|-----------------|  
|[operator=](#operator_eq)|割り当てる、`combinable`オブジェクトから`combinable`オブジェクトです。|  
  
## <a name="remarks"></a>コメント  
 詳細については、次を参照してください。[並列コンテナーと並列オブジェクト](../../../parallel/concrt/parallel-containers-and-objects.md)します。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 `combinable`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** ppl.h  
  
 **名前空間:** concurrency  
  
##  <a name="clear"></a>オフ 

 以前の使用法から中間の計算結果をクリアします。  
  
```
void clear();
```  
  
##  <a name="ctor"></a>組み合わせ可能 

 新しい `combinable` オブジェクトを構築します。  
  
```
combinable();

template <typename _Function>
explicit combinable(_Function _FnInitialize);

combinable(const combinable& _Copy);
```  
  
### <a name="parameters"></a>パラメーター  
 `_Function`  
 初期化ファンクタ オブジェクトの型。  
  
 `_FnInitialize`  
 型の新しい各スレッド プライベート値を初期化するために呼び出される関数`T`します。 シグネチャを持つ関数呼び出し演算子をサポートする必要があります`T ()`します。  
  
 `_Copy`  
 既存の`combinable`この&1; つにコピーされるオブジェクト。  
  
### <a name="remarks"></a>コメント  
 最初のコンス トラクターが型の既定のコンス トラクターを持つ新しい要素を初期化します`T`します。  
  
 2 番目のコンス トラクターとして指定された初期化ファンクタを使用して新しい要素の初期化、`_FnInitialize`パラメーター。  
  
 3 番目のコンス トラクターは、コピー コンス トラクターです。  
  
##  <a name="dtor"></a>~ combinable 

 `combinable` オブジェクトを破棄します。  
  
```
~combinable();
```  
  
##  <a name="combine"></a>結合 

 指定された結合ファンクタを呼び出すことによって、スレッド ローカルのサブ計算のセットから最終的な値を計算します。  
  
```
template<typename _Function>
T combine(_Function _FnCombine) const;
```  
  
### <a name="parameters"></a>パラメーター  
 `_Function`  
 2 つのスレッド ローカルのサブ計算を結合するときに呼び出される関数オブジェクトの型。  
  
 `_FnCombine`  
 サブ計算を結合するためのファンクタ。 シグニチャは`T (T, T)`または`T (const T&, const T&)`と結合規則および可換性があります。  
  
### <a name="return-value"></a>戻り値  
 すべてのスレッド プライベート サブ計算を組み合わせることの最終的な結果です。  
  
##  <a name="combine_each"></a>combine_each 

 スレッド ローカルのサブ計算ごとに&1; 回、指定された結合ファンクタを呼び出すことによって、スレッド ローカルのサブ計算のセットから最終的な値を計算します。 最終的な結果は、関数オブジェクトによっては累積されます。  
  
```
template<typename _Function>
void combine_each(_Function _FnCombine) const;
```  
  
### <a name="parameters"></a>パラメーター  
 `_Function`  
 シングル スレッド ローカルのサブ計算を結合するときに呼び出される関数オブジェクトの型。  
  
 `_FnCombine`  
 1 つのサブ計算を結合するためのファンクタ。 シグニチャは`void (T)`または`void (const T&)`、結合規則および可換にする必要があります。  
  
##  <a name="local"></a>地元の 

 スレッド プライベート サブ計算への参照を返します。  
  
```
T& local();

T& local(bool& _Exists);
```  
  
### <a name="parameters"></a>パラメーター  
 `_Exists`  
 ブール値への参照。 この引数によって参照されるブール値に設定されます`true`サブ計算が既にこのスレッドに存在し、設定かどうか`false`場合、これは、このスレッドで最初のサブ計算します。  
  
### <a name="return-value"></a>戻り値  
 スレッド プライベート サブ計算への参照。  
  
##  <a name="operator_eq"></a>演算子 = 

 割り当てる、`combinable`オブジェクトから`combinable`オブジェクトです。  
  
```
combinable& operator= (const combinable& _Copy);
```  
  
### <a name="parameters"></a>パラメーター  
 `_Copy`  
 既存の`combinable`この&1; つにコピーされるオブジェクト。  
  
### <a name="return-value"></a>戻り値  
 この `combinable` オブジェクトへの参照。  
  
## <a name="see-also"></a>関連項目  
 [concurrency 名前空間](concurrency-namespace.md)

