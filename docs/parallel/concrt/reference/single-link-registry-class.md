---
title: "single_link_registry クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- single_link_registry
- AGENTS/concurrency::single_link_registry
- AGENTS/concurrency::single_link_registry::single_link_registry
- AGENTS/concurrency::single_link_registry::add
- AGENTS/concurrency::single_link_registry::begin
- AGENTS/concurrency::single_link_registry::contains
- AGENTS/concurrency::single_link_registry::count
- AGENTS/concurrency::single_link_registry::remove
dev_langs:
- C++
helpviewer_keywords:
- single_link_registry class
ms.assetid: 09540a4e-c34e-4ff9-af49-21b8612b6ab3
caps.latest.revision: 19
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
ms.openlocfilehash: fc99e9af586520d60c20302e8b828a188df9efda
ms.lasthandoff: 03/17/2017

---
# <a name="singlelinkregistry-class"></a>single_link_registry クラス
`single_link_registry` オブジェクトは、単一のソース ブロックまたはターゲット ブロックのみを管理する `network_link_registry` です。  
  
## <a name="syntax"></a>構文  
  
```
template<class _Block>
class single_link_registry : public network_link_registry<_Block>;
```  
  
#### <a name="parameters"></a>パラメーター  
 `_Block`  
 ブロックのデータ型に格納されている、`single_link_registry`オブジェクトです。  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[single_link_registry](#ctor)|`single_link_registry` オブジェクトを構築します。|  
|[~ single_link_registry デストラクター](#dtor)|`single_link_registry` オブジェクトを破棄します。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[add](#add)|リンクを追加、`single_link_registry`オブジェクトです。 (上書き[network_link_registry::add](network-link-registry-class.md#add))。|  
|[begin](#begin)|最初の要素を反復子を返します、`single_link_registry`オブジェクトです。 (上書き[network_link_registry::begin](network-link-registry-class.md#begin))。|  
|[含まれています](#contains)|検索、`single_link_registry`の指定されたブロックのオブジェクト。 (上書き[network_link_registry::contains](network-link-registry-class.md#contains))。|  
|[count](#count)|内の項目の数をカウント、`single_link_registry`オブジェクトです。 (上書き[network_link_registry::count](network-link-registry-class.md#count))。|  
|[remove](#remove)|リンクを削除、`single_link_registry`オブジェクトです。 (上書き[network_link_registry::remove](network-link-registry-class.md#remove))。|  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [network_link_registry](network-link-registry-class.md)  
  
 `single_link_registry`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** agents.h  
  
 **名前空間:** concurrency  
  
##  <a name="add"></a>追加 

 リンクを追加、`single_link_registry`オブジェクトです。  
  
```
virtual void add(_EType _Link);
```  
  
### <a name="parameters"></a>パラメーター  
 `_Link`  
 追加するブロックへのポインター。  
  
### <a name="remarks"></a>コメント  
 メソッドをスロー、 [invalid_link_target](invalid-link-target-class.md)このレジストリにリンクが存在する場合に例外です。  
  
##  <a name="begin"></a>開始 

 最初の要素を反復子を返します、`single_link_registry`オブジェクトです。  
  
```
virtual iterator begin();
```  
  
### <a name="return-value"></a>戻り値  
 最初の要素を指定する反復子、`single_link_registry`オブジェクトです。  
  
### <a name="remarks"></a>コメント  
 終了状態で示されます、`NULL`リンクします。  
  
##  <a name="contains"></a>含まれています 

 検索、`single_link_registry`の指定されたブロックのオブジェクト。  
  
```
virtual bool contains(_EType _Link);
```  
  
### <a name="parameters"></a>パラメーター  
 `_Link`  
 内で検索するのには、ブロックへのポインター、`single_link_registry`オブジェクトです。  
  
### <a name="return-value"></a>戻り値  
 `true`リンクが見つからなかった場合`false`それ以外の場合。  
  
##  <a name="count"></a>カウント 

 内の項目の数をカウント、`single_link_registry`オブジェクトです。  
  
```
virtual size_t count();
```  
  
### <a name="return-value"></a>戻り値  
 内の項目数、`single_link_registry`オブジェクトです。  
  
##  <a name="remove"></a>削除します。 

 リンクを削除、`single_link_registry`オブジェクトです。  
  
```
virtual bool remove(_EType _Link);
```  
  
### <a name="parameters"></a>パラメーター  
 `_Link`  
 削除する場合はブロックへのポインターが見つかりました。  
  
### <a name="return-value"></a>戻り値  
 `true`リンクが検出され削除されると、`false`それ以外の場合。  
  
##  <a name="ctor"></a>single_link_registry 

 `single_link_registry` オブジェクトを構築します。  
  
```
single_link_registry();
```  
  
##  <a name="dtor"></a>~ single_link_registry 

 `single_link_registry` オブジェクトを破棄します。  
  
```
virtual ~single_link_registry();
```  
  
### <a name="remarks"></a>コメント  
 メソッドをスロー、 [invalid_operation](invalid-operation-class.md)リンクが削除される前に呼び出された場合に例外です。  
  
## <a name="see-also"></a>関連項目  
 [同時実行 Namespace](concurrency-namespace.md)   
 [multi_link_registry クラス](multi-link-registry-class.md)

