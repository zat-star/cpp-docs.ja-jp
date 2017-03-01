---
title: "critical_section クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- concrt/concurrency::critical_section
dev_langs:
- C++
helpviewer_keywords:
- critical_section class
ms.assetid: fa3c89d6-be5d-4d1b-bddb-8232814e6cf6
caps.latest.revision: 23
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
ms.openlocfilehash: 20a150c1aedbd9d78c84187bf29e6284a248fbc7
ms.lasthandoff: 02/24/2017

---
# <a name="criticalsection-class"></a>critical_section クラス
同時実行ランタイムを明示的に認識する再入不可能なミューテックスです。  
  
## <a name="syntax"></a>構文  
  
```
class critical_section;
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-typedefs"></a>パブリック typedef  
  
|名前|説明|  
|----------|-----------------|  
|`native_handle_type`|`critical_section` オブジェクトへの参照。|  
  
### <a name="public-classes"></a>パブリック クラス  
  
|名前|説明|  
|----------|-----------------|  
|[critical_section::scoped_lock クラス](#critical_section__scoped_lock_class)|例外安全な RAII ラッパー、`critical_section`オブジェクトです。|  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[critical_section コンス トラクター](#ctor)|新しい重要なセクションを作成します。|  
|[~ critical_section デストラクター](#dtor)|クリティカル セクションを破棄します。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[lock メソッド](#lock)|この重要なセクションを取得します。|  
|[native_handle メソッド](#native_handle)|1 つが存在する場合は、プラットフォーム固有のネイティブ ハンドルを返します。|  
|[try_lock メソッド](#try_lock)|ブロックすることがなく、ロックの取得を試みます。|  
|[try_lock_for メソッド](#try_lock_for)|ミリ秒数を特定のブロックすることがなく、ロックの取得を試みます。|  
|[unlock メソッド](#unlock)|クリティカル セクションのロックを解除します。|  
  
## <a name="remarks"></a>コメント  
 詳細については、次を参照してください。[同期データ構造](../../../parallel/concrt/synchronization-data-structures.md)します。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 `critical_section`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** concrt.h  
  
 **名前空間:** concurrency  
  
##  <a name="a-namectora-criticalsection"></a><a name="ctor"></a>critical_section 

 新しい重要なセクションを作成します。  
  
```
critical_section();
```  
  
##  <a name="a-namedtora-criticalsection"></a><a name="dtor"></a>~ critical_section 

 クリティカル セクションを破棄します。  
  
```
~critical_section();
```  
  
### <a name="remarks"></a>コメント  
 デストラクターが実行されるときに、ロックが保持されなく必要です。 ロックを消滅させるためにクリティカル セクションを保持した未定義の動作です。  
  
##  <a name="a-namelocka-lock"></a><a name="lock"></a>ロック 

 この重要なセクションを取得します。  
  
```
void lock();
```  
  
### <a name="remarks"></a>コメント  
 利用する方が安全では多くの場合、 [scoped_lock](#critical_section__scoped_lock_class)取得および解放するコンス トラクター、`critical_section`例外オブジェクト安全な方法です。  
  
 ロックが呼び出し元のコンテキストによって既に保持されている場合、 [improper_lock](improper-lock-class.md)例外がスローされます。  
  
##  <a name="a-namenativehandlea-nativehandle"></a><a name="native_handle"></a>native_handle 

 1 つが存在する場合は、プラットフォーム固有のネイティブ ハンドルを返します。  
  
```
native_handle_type native_handle();
```  
  
### <a name="return-value"></a>戻り値  
 クリティカル セクションへの参照。  
  
### <a name="remarks"></a>コメント  
 A`critical_section`オブジェクトは、Windows オペレーティング システムのプラットフォームの特定ネイティブ ハンドルに関連付けられていません。 メソッドは、単にオブジェクト自体への参照を返します。  
  
##  <a name="a-namecriticalsectionscopedlockclassa--criticalsectionscopedlock-class"></a><a name="critical_section__scoped_lock_class"></a>critical_section::scoped_lock クラス  
 例外安全な RAII ラッパー、`critical_section`オブジェクトです。  
  
```
class scoped_lock;
```  
  
##  <a name="a-namecriticalsectionscopedlockctora-scopedlockscopedlock"></a><a name="critical_section__scoped_lock_ctor"></a>scoped_lock::scoped_lock 

 構築、`scoped_lock`オブジェクトを取得し、`critical_section`で渡されるオブジェクト、`_Critical_section`パラメーター。 クリティカル セクションが別のスレッドによって保持されている場合、この呼び出しはブロックされます。  
  
```
explicit _CRTIMP scoped_lock(critical_section& _Critical_section);
```  
  
### <a name="parameters"></a>パラメーター  
 `_Critical_section`  
 ロックするクリティカル セクションです。  
  
##  <a name="a-namecriticalsectionscopedlockdtora-scopedlockscopedlock"></a><a name="critical_section__scoped_lock_dtor"></a>scoped_lock:: ~ scoped_lock 

 破棄、`scoped_lock`オブジェクトし、そのコンス トラクターでクリティカル セクションを解放します。  
  
```
~scoped_lock();
```  
  
##  <a name="a-nametrylocka-trylock"></a><a name="try_lock"></a>try_lock 

 ブロックすることがなく、ロックの取得を試みます。  
  
```
bool try_lock();
```  
  
### <a name="return-value"></a>戻り値  
 ロックが取得された場合、値`true`。 そうしないと、値`false`です。  
  
##  <a name="a-nametrylockfora-trylockfor"></a><a name="try_lock_for"></a>try_lock_for 

 ミリ秒数を特定のブロックすることがなく、ロックの取得を試みます。  
  
```
bool try_lock_for(unsigned int _Timeout);
```  
  
### <a name="parameters"></a>パラメーター  
 `_Timeout`  
 タイムアウトするまでに待機するミリ秒数。  
  
### <a name="return-value"></a>戻り値  
 ロックが取得された場合、値`true`。 そうしないと、値`false`です。  
  
##  <a name="a-nameunlocka-unlock"></a><a name="unlock"></a>ロックを解除します。 

 クリティカル セクションのロックを解除します。  
  
```
void unlock();
```  
  
## <a name="see-also"></a>関連項目  
 [同時実行 Namespace](concurrency-namespace.md)   
 [reader_writer_lock クラス](reader-writer-lock-class.md)

