---
title: "source_link_manager クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- source_link_manager
- AGENTS/concurrency::source_link_manager
- AGENTS/concurrency::source_link_manager::source_link_manager
- AGENTS/concurrency::source_link_manager::add
- AGENTS/concurrency::source_link_manager::begin
- AGENTS/concurrency::source_link_manager::contains
- AGENTS/concurrency::source_link_manager::count
- AGENTS/concurrency::source_link_manager::reference
- AGENTS/concurrency::source_link_manager::register_target_block
- AGENTS/concurrency::source_link_manager::release
- AGENTS/concurrency::source_link_manager::remove
- AGENTS/concurrency::source_link_manager::set_bound
dev_langs:
- C++
helpviewer_keywords:
- source_link_manager class
ms.assetid: 287487cf-e0fe-4c35-aa3c-24f081d1ddae
caps.latest.revision: 17
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 5faef5bd1be6cc02d6614a6f6193c74167a8ff23
ms.openlocfilehash: 8e875fdd02a42e1cb1c144b0b7da07a1f4e9a184
ms.contentlocale: ja-jp
ms.lasthandoff: 03/17/2017

---
# <a name="sourcelinkmanager-class"></a>source_link_manager クラス
`source_link_manager` オブジェクトは、`ISource` ブロックへのメッセージング ブロック ネットワーク リンクを管理します。  
  
## <a name="syntax"></a>構文  
  
```
template<class _LinkRegistry>
class source_link_manager;
```  
  
#### <a name="parameters"></a>パラメーター  
 `_LinkRegistry`  
 ネットワーク リンク レジストリ。  
  
## <a name="members"></a>メンバー  
  
### <a name="public-typedefs"></a>パブリック typedef  
  
|名前|説明|  
|----------|-----------------|  
|`const_pointer`|ポインターを提供する型、`const`内の要素、`source_link_manager`オブジェクトです。|  
|`const_reference`|参照を提供する型、`const`に要素が格納されている、`source_link_manager`の読み取りと const の操作を実行するオブジェクト。|  
|`iterator`|読み取りまたはの任意の要素を変更できる、反復子を提供する型、`source_link_manager`オブジェクトです。|  
|`type`|によって管理されているリンクのレジストリの種類、`source_link_manager`オブジェクトです。|  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[source_link_manager](#ctor)|`source_link_manager` オブジェクトを構築します。|  
|[~ source_link_manager デストラクター](#dtor)|`source_link_manager` オブジェクトを破棄します。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[add](#add)|ソースへのリンクを追加、`source_link_manager`オブジェクトです。|  
|[begin](#begin)|最初の要素を反復子を返します、`source_link_manager`オブジェクトです。|  
|[含まれています](#contains)|検索、`network_link_registry`この`source_link_manager`の指定されたブロックのオブジェクト。|  
|[count](#count)|リンクされたブロックの数をカウント、`source_link_manager`オブジェクトです。|  
|[reference](#reference)|上の参照を取得し、`source_link_manager`オブジェクトです。|  
|[register_target_block](#register_target_block)|これを保持しているターゲット ブロックを登録`source_link_manager`オブジェクトです。|  
|[release](#release)|参照を解放、`source_link_manager`オブジェクトです。|  
|[remove](#remove)|リンクを削除、`source_link_manager`オブジェクトです。|  
|[set_bound](#set_bound)|これに追加できる送信元のリンクの最大数を設定`source_link_manager`オブジェクトです。|  
  
## <a name="remarks"></a>コメント  
 現時点では、ソース ブロックは、参照カウントされます。 これは、上、`network_link_registry`のリンクを同時アクセスを許可され、コールバックをとおしてリンクを参照する機能を提供するオブジェクト。 メッセージ ブロック ( `target_block`s または`propagator_block`s)、送信元のリンクに、このクラスを使用する必要があります。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 `source_link_manager`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** agents.h  
  
 **名前空間:** concurrency  
  
##  <a name="add"></a>追加 

 ソースへのリンクを追加、`source_link_manager`オブジェクトです。  
  
```
void add(_EType _Link);
```  
  
### <a name="parameters"></a>パラメーター  
 `_Link`  
 追加するブロックへのポインター。  
  
##  <a name="begin"></a>開始 

 最初の要素を反復子を返します、`source_link_manager`オブジェクトです。  
  
```
iterator begin();
```  
  
### <a name="return-value"></a>戻り値  
 最初の要素を指定する反復子、`source_link_manager`オブジェクトです。  
  
### <a name="remarks"></a>コメント  
 によって、反復子の最終の状態が示されている、`NULL`リンクします。  
  
##  <a name="contains"></a>含まれています 

 検索、`network_link_registry`この`source_link_manager`の指定されたブロックのオブジェクト。  
  
```
bool contains(_EType _Link);
```  
  
### <a name="parameters"></a>パラメーター  
 `_Link`  
 内で検索するのには、ブロックへのポインター、`source_link_manager`オブジェクトです。  
  
### <a name="return-value"></a>戻り値  
 `true`指定されたブロックが見つかった場合`false`それ以外の場合。  
  
##  <a name="count"></a>カウント 

 リンクされたブロックの数をカウント、`source_link_manager`オブジェクトです。  
  
```
size_t count();
```  
  
### <a name="return-value"></a>戻り値  
 リンクされたブロックの数、`source_link_manager`オブジェクトです。  
  
##  <a name="reference"></a>参照 

 上の参照を取得し、`source_link_manager`オブジェクトです。  
  
```
void reference();
```  
  
##  <a name="register_target_block"></a>register_target_block 

 これを保持しているターゲット ブロックを登録`source_link_manager`オブジェクトです。  
  
```
void register_target_block(_Inout_ ITarget<typename _Block::source_type>* _PTarget);
```  
  
### <a name="parameters"></a>パラメーター  
 `_PTarget`  
 これを保持しているターゲット ブロック`source_link_manager`オブジェクトです。  
  
##  <a name="release"></a>リリース 

 参照を解放、`source_link_manager`オブジェクトです。  
  
```
void release();
```  
  
##  <a name="remove"></a>削除します。 

 リンクを削除、`source_link_manager`オブジェクトです。  
  
```
bool remove(_EType _Link);
```  
  
### <a name="parameters"></a>パラメーター  
 `_Link`  
 削除する場合はブロックへのポインターが見つかりました。  
  
### <a name="return-value"></a>戻り値  
 `true`リンクが検出され削除されると、`false`それ以外の場合。  
  
##  <a name="set_bound"></a>set_bound 

 これに追加できる送信元のリンクの最大数を設定`source_link_manager`オブジェクトです。  
  
```
void set_bound(size_t _MaxLinks);
```  
  
### <a name="parameters"></a>パラメーター  
 `_MaxLinks`  
 リンクの最大数。  
  
##  <a name="ctor"></a>source_link_manager 

 `source_link_manager` オブジェクトを構築します。  
  
```
source_link_manager();
```  
  
##  <a name="dtor"></a>~ source_link_manager 

 `source_link_manager` オブジェクトを破棄します。  
  
```
~source_link_manager();
```  
  
## <a name="see-also"></a>関連項目  
 [同時実行 Namespace](concurrency-namespace.md)   
 [single_link_registry クラス](single-link-registry-class.md)   
 [multi_link_registry クラス](multi-link-registry-class.md)

