---
title: "network_link_registry クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- agents/concurrency::network_link_registry
dev_langs:
- C++
helpviewer_keywords:
- network_link_registry class
ms.assetid: 3e7b4097-09f1-4252-964e-b15b8f7f7fc6
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
ms.sourcegitcommit: fc190feb08d9b221cd1cc21a9c91ad567c86c848
ms.openlocfilehash: 8b39ab676db0072d279ee4058693769ef6f7eb3f
ms.lasthandoff: 02/24/2017

---
# <a name="networklinkregistry-class"></a>network_link_registry クラス
`network_link_registry` 抽象基底クラスによって、ソース ブロックとターゲット ブロック間のリンクを管理します。  
  
## <a name="syntax"></a>構文  
  
```
template<class _Block>
class network_link_registry;
```  
  
#### <a name="parameters"></a>パラメーター  
 `_Block`  
 ブロックのデータ型に格納されている、`network_link_registry`です。  
  
## <a name="members"></a>メンバー  
  
### <a name="public-typedefs"></a>パブリック typedef  
  
|名前|説明|  
|----------|-----------------|  
|`const_pointer`|ポインターを提供する型、`const`内の要素、`network_link_registry`オブジェクトです。|  
|`const_reference`|参照を提供する型、`const`に要素が格納されている、`network_link_registry`の読み取りと const の操作を実行するオブジェクト。|  
|`iterator`|読み取りまたはの任意の要素を変更できる、反復子を提供する型、`network_link_registry`オブジェクトです。|  
|`type`|格納されているブロックの型を表す型、`network_link_registry`オブジェクトです。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[メソッドを追加します。](#add)|派生クラスでオーバーライドされた場合へのリンクを追加、`network_link_registry`オブジェクトです。|  
|[begin メソッド](#begin)|派生クラスでオーバーライドされると、反復子を返しますの最初の要素を`network_link_registry`オブジェクトです。|  
|[メソッドが含まれています](#contains)|派生クラスでオーバーライドされると、検索、`network_link_registry`の指定されたブロックのオブジェクト。|  
|[count メソッド](#count)|派生クラスでオーバーライドされると、内の項目数を返す、`network_link_registry`オブジェクトです。|  
|[remove メソッド](#remove)|派生クラスでオーバーライドされると、削除から指定されたブロック、`network_link_registry`オブジェクトです。|  
  
## <a name="remarks"></a>コメント  
 `network link registry`への同時アクセスの安全ではありません。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 `network_link_registry`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** agents.h  
  
 **名前空間:** concurrency  
  
##  <a name="a-nameadda-add"></a><a name="add"></a>追加 

 派生クラスでオーバーライドされた場合へのリンクを追加、`network_link_registry`オブジェクトです。  
  
```
virtual void add(_EType _Link) = 0;
```  
  
### <a name="parameters"></a>パラメーター  
 `_Link`  
 追加するブロックへのポインター。  
  
##  <a name="a-namebegina-begin"></a><a name="begin"></a>開始 

 派生クラスでオーバーライドされると、反復子を返しますの最初の要素を`network_link_registry`オブジェクトです。  
  
```
virtual iterator begin() = 0;
```  
  
### <a name="return-value"></a>戻り値  
 最初の要素を指定する反復子、`network_link_registry`オブジェクトです。  
  
### <a name="remarks"></a>コメント  
 によって、反復子の最終の状態が示されている、`NULL`リンクします。  
  
##  <a name="a-namecontainsa-contains"></a><a name="contains"></a>含まれています 

 派生クラスでオーバーライドされると、検索、`network_link_registry`の指定されたブロックのオブジェクト。  
  
```
virtual bool contains(_EType _Link) = 0;
```  
  
### <a name="parameters"></a>パラメーター  
 `_Link`  
 検索対象となるブロックへのポインター、`network_link_registry`オブジェクトです。  
  
### <a name="return-value"></a>戻り値  
 `true`ブロックが見つかった場合`false`それ以外の場合。  
  
##  <a name="a-namecounta-count"></a><a name="count"></a>カウント 

 派生クラスでオーバーライドされると、内の項目数を返す、`network_link_registry`オブジェクトです。  
  
```
virtual size_t count() = 0;
```  
  
### <a name="return-value"></a>戻り値  
 内の項目数、`network_link_registry`オブジェクトです。  
  
##  <a name="a-nameremovea-remove"></a><a name="remove"></a>削除します。 

 派生クラスでオーバーライドされると、削除から指定されたブロック、`network_link_registry`オブジェクトです。  
  
```
virtual bool remove(_EType _Link) = 0;
```  
  
### <a name="parameters"></a>パラメーター  
 `_Link`  
 削除する場合はブロックへのポインターが見つかりました。  
  
### <a name="return-value"></a>戻り値  
 `true`リンクが検出され削除されると、`false`それ以外の場合。  
  
## <a name="see-also"></a>関連項目  
 [同時実行 Namespace](concurrency-namespace.md)   
 [single_link_registry クラス](single-link-registry-class.md)   
 [multi_link_registry クラス](multi-link-registry-class.md)

