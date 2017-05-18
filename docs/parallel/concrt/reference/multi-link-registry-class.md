---
title: "multi_link_registry クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- multi_link_registry
- AGENTS/concurrency::multi_link_registry
- AGENTS/concurrency::multi_link_registry::multi_link_registry
- AGENTS/concurrency::multi_link_registry::add
- AGENTS/concurrency::multi_link_registry::begin
- AGENTS/concurrency::multi_link_registry::contains
- AGENTS/concurrency::multi_link_registry::count
- AGENTS/concurrency::multi_link_registry::remove
- AGENTS/concurrency::multi_link_registry::set_bound
dev_langs:
- C++
helpviewer_keywords:
- multi_link_registry class
ms.assetid: b2aa73a8-e8a6-4255-b117-d07530c328b2
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 5faef5bd1be6cc02d6614a6f6193c74167a8ff23
ms.openlocfilehash: b52ee20ed16a4ce8d0b9f11b6acf25112464b49b
ms.contentlocale: ja-jp
ms.lasthandoff: 03/17/2017

---
# <a name="multilinkregistry-class"></a>multi_link_registry クラス
`multi_link_registry` オブジェクトは、複数のソース ブロックまたは複数のターゲット ブロックを管理する `network_link_registry` です。  
  
## <a name="syntax"></a>構文  
  
```
template<class _Block>
class multi_link_registry : public network_link_registry<_Block>;
```  
  
#### <a name="parameters"></a>パラメーター  
 `_Block`  
 ブロックのデータ型に格納されている、`multi_link_registry`オブジェクトです。  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[multi_link_registry](#ctor)|`multi_link_registry` オブジェクトを構築します。|  
|[~ multi_link_registry デストラクター](#dtor)|`multi_link_registry` オブジェクトを破棄します。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[add](#add)|リンクを追加、`multi_link_registry`オブジェクトです。 (上書き[network_link_registry::add](network-link-registry-class.md#add))。|  
|[begin](#begin)|最初の要素を反復子を返します、`multi_link_registry`オブジェクトです。 (上書き[network_link_registry::begin](network-link-registry-class.md#begin))。|  
|[含まれています](#contains)|検索、`multi_link_registry`の指定されたブロックのオブジェクト。 (上書き[network_link_registry::contains](network-link-registry-class.md#contains))。|  
|[count](#count)|内の項目の数をカウント、`multi_link_registry`オブジェクトです。 (上書き[network_link_registry::count](network-link-registry-class.md#count))。|  
|[remove](#remove)|リンクを削除、`multi_link_registry`オブジェクトです。 (上書き[network_link_registry::remove](network-link-registry-class.md#remove))。|  
|[set_bound](#set_bound)|リンクの数に上限を設定、`multi_link_registry`オブジェクトを保持できます。|  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [network_link_registry](network-link-registry-class.md)  
  
 `multi_link_registry`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** agents.h  
  
 **名前空間:** concurrency  
  
##  <a name="add"></a>追加 

 リンクを追加、`multi_link_registry`オブジェクトです。  
  
```
virtual void add(_EType _Link);
```  
  
### <a name="parameters"></a>パラメーター  
 `_Link`  
 追加するブロックへのポインター。  
  
### <a name="remarks"></a>コメント  
 メソッドをスロー、 [invalid_link_target](invalid-link-target-class.md)例外のリンクが、レジストリに存在する場合、または場合は、バインドが既にで設定された、`set_bound`関数とのリンクは削除されました。  
  
##  <a name="begin"></a>開始 

 最初の要素を反復子を返します、`multi_link_registry`オブジェクトです。  
  
```
virtual iterator begin();
```  
  
### <a name="return-value"></a>戻り値  
 最初の要素を指定する反復子、`multi_link_registry`オブジェクトです。  
  
### <a name="remarks"></a>コメント  
 終了状態で示されます、`NULL`リンクします。  
  
##  <a name="contains"></a>含まれています 

 検索、`multi_link_registry`の指定されたブロックのオブジェクト。  
  
```
virtual bool contains(_EType _Link);
```  
  
### <a name="parameters"></a>パラメーター  
 `_Link`  
 内で検索するのには、ブロックへのポインター、`multi_link_registry`オブジェクトです。  
  
### <a name="return-value"></a>戻り値  
 `true`指定されたブロックが見つかった場合`false`それ以外の場合。  
  
##  <a name="count"></a>カウント 

 内の項目の数をカウント、`multi_link_registry`オブジェクトです。  
  
```
virtual size_t count();
```  
  
### <a name="return-value"></a>戻り値  
 内の項目数、`multi_link_registry`オブジェクトです。  
  
##  <a name="ctor"></a>multi_link_registry 

 `multi_link_registry` オブジェクトを構築します。  
  
```
multi_link_registry();
```  
  
##  <a name="dtor"></a>~ multi_link_registry 

 `multi_link_registry` オブジェクトを破棄します。  
  
```
virtual ~multi_link_registry();
```  
  
### <a name="remarks"></a>コメント  
 メソッドをスロー、 [invalid_operation](invalid-operation-class.md)すべてのリンクを削除する前に呼び出す場合に例外です。  
  
##  <a name="remove"></a>削除します。 

 リンクを削除、`multi_link_registry`オブジェクトです。  
  
```
virtual bool remove(_EType _Link);
```  
  
### <a name="parameters"></a>パラメーター  
 `_Link`  
 削除する場合はブロックへのポインターが見つかりました。  
  
### <a name="return-value"></a>戻り値  
 `true`リンクが検出され削除されると、`false`それ以外の場合。  
  
##  <a name="set_bound"></a>set_bound 

 リンクの数に上限を設定、`multi_link_registry`オブジェクトを保持できます。  
  
```
void set_bound(size_t _MaxLinks);
```  
  
### <a name="parameters"></a>パラメーター  
 `_MaxLinks`  
 リンクの最大数、`multi_link_registry`オブジェクトを保持できます。  
  
### <a name="remarks"></a>コメント  
 制限を設定すると、エントリのリンクを解除すると、 `multi_link_registry` 、変更できない状態に移行するオブジェクトへの呼び出しをさらに、`add`をスロー、`invalid_link_target`例外です。  
  
## <a name="see-also"></a>関連項目  
 [同時実行 Namespace](concurrency-namespace.md)   
 [single_link_registry クラス](single-link-registry-class.md)

