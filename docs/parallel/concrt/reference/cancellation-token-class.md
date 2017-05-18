---
title: "cancellation_token クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- cancellation_token
- PPLCANCELLATION_TOKEN/concurrency::cancellation_token
- PPLCANCELLATION_TOKEN/concurrency::cancellation_token::cancellation_token
- PPLCANCELLATION_TOKEN/concurrency::cancellation_token::deregister_callback
- PPLCANCELLATION_TOKEN/concurrency::cancellation_token::is_cancelable
- PPLCANCELLATION_TOKEN/concurrency::cancellation_token::is_canceled
- PPLCANCELLATION_TOKEN/concurrency::cancellation_token::none
- PPLCANCELLATION_TOKEN/concurrency::cancellation_token::register_callback
dev_langs:
- C++
helpviewer_keywords:
- cancellation_token class
ms.assetid: 2787df2b-e9d3-440e-bfd0-841a46a9835f
caps.latest.revision: 10
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
ms.openlocfilehash: d17505a117c0affd8106afad9004e6ec86602a26
ms.contentlocale: ja-jp
ms.lasthandoff: 03/17/2017

---
# <a name="cancellationtoken-class"></a>cancellation_token クラス
`cancellation_token` クラスは、ある操作の取り消しが要求されたかどうかを判断する機能を表します。 特定のトークンを `task_group`、`structured_task_group`、または `task` に関連付けると、暗黙的な取り消しを指定できます。 関連付けられた `cancellation_token_source` が取り消されたときに、取り消すためにポーリングしたり、コールバックを登録したりすることもできます。  
  
## <a name="syntax"></a>構文  
  
```
class cancellation_token;
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[cancellation_token](#ctor)||  
|[~ cancellation_token デストラクター](#dtor)||  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[deregister_callback](#deregister_callback)|登録時に返された `register` オブジェクトに基づく `cancellation_token_registration` メソッドによって以前に登録されたコールバックを削除します。|  
|[is_cancelable](#is_cancelable)|このトークンを取り消すことができるかどうかを示す値を返します。|  
|[is_canceled](#is_canceled)|トークンが取り消された場合は `true` を返します。|  
|[none](#none)|取り消しの対象とはならないキャンセル トークンを返します。|  
|[register_callback](#register_callback)|コールバック関数をトークンに登録します。 トークンが取り消された場合、コールバックが行われます。 このメソッドが呼び出された時点で既にコールバックが取り消されている場合、コールバックは即座に同期的に行われることに注意してください。|  
  
### <a name="public-operators"></a>パブリック演算子  
  
|名前|説明|  
|----------|-----------------|  
|[operator!=](#operator_neq)||  
|[operator=](#operator_eq)||  
|[operator==](#operator_eq_eq)||  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 `cancellation_token`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** pplcancellation_token.h  
  
 **名前空間:** concurrency  
  
##  <a name="dtor"></a>~ cancellation_token 

```
~cancellation_token();
```  
  
##  <a name="ctor"></a>cancellation_token 

```
cancellation_token(const cancellation_token& _Src);

cancellation_token(cancellation_token&& _Src);
```  
  
### <a name="parameters"></a>パラメーター  
 `_Src`  
  
##  <a name="deregister_callback"></a>deregister_callback 

 登録時に返された `register` オブジェクトに基づく `cancellation_token_registration` メソッドによって以前に登録されたコールバックを削除します。  
  
```
void deregister_callback(const cancellation_token_registration& _Registration) const;
```  
  
### <a name="parameters"></a>パラメーター  
 `_Registration`  
 登録解除されるコールバックに対応する `cancellation_token_registration` オブジェクト。 このトークンは、`register` メソッドの呼び出しによって既に返されている必要があります。  
  
##  <a name="is_cancelable"></a>is_cancelable 

 このトークンを取り消すことができるかどうかを示す値を返します。  
  
```
bool is_cancelable() const;
```  
  
### <a name="return-value"></a>戻り値  
 このトークンを取り消すことができるかどうかを示す値。  
  
##  <a name="is_canceled"></a>is_canceled 

 トークンが取り消された場合は `true` を返します。  
  
```
bool is_canceled() const;
```  
  
### <a name="return-value"></a>戻り値  
 トークンが取り消されている場合は、値 `true` を返します。それ以外の場合は、値 `false` を返します。  
  
##  <a name="none"></a>[なし] 

 取り消しの対象とはならないキャンセル トークンを返します。  
  
```
static cancellation_token none();
```  
  
### <a name="return-value"></a>戻り値  
 取り消すことができないキャンセル トークン。  
  
##  <a name="operator_neq"></a>operator! = 

```
bool operator!= (const cancellation_token& _Src) const;
```  
  
### <a name="parameters"></a>パラメーター  
 `_Src`  
  
### <a name="return-value"></a>戻り値  
  
##  <a name="operator_eq"></a>演算子 = 

```
cancellation_token& operator= (const cancellation_token& _Src);

cancellation_token& operator= (cancellation_token&& _Src);
```  
  
### <a name="parameters"></a>パラメーター  
 `_Src`  
  
### <a name="return-value"></a>戻り値  
  
##  <a name="operator_eq_eq"></a>演算子 = = 

```
bool operator== (const cancellation_token& _Src) const;
```  
  
### <a name="parameters"></a>パラメーター  
 `_Src`  
  
### <a name="return-value"></a>戻り値  
  
##  <a name="register_callback"></a>register_callback 

 コールバック関数をトークンに登録します。 トークンが取り消された場合、コールバックが行われます。 このメソッドが呼び出された時点で既にトークンが取り消されている場合、コールバックは即座に同期的に行われることに注意してください。  
  
```
template<typename _Function>
::Concurrency::cancellation_token_registration register_callback(const _Function& _Func) const;
```  
  
### <a name="parameters"></a>パラメーター  
 `_Function`  
 この `cancellation_token` が取り消されるときにコールバックされる関数オブジェクトの型。  
  
 `_Func`  
 この `cancellation_token` が取り消されるときにコールバックされる関数オブジェクト。  
  
### <a name="return-value"></a>戻り値  
 `cancellation_token_registration` メソッドで利用できる `deregister` オブジェクト。その利用目的は、以前に登録されたコールバックの登録を解除し、コールバックが行われないようにすることです。 メソッドがスローされます、 [invalid_operation](invalid-operation-class.md)例外に対してを呼び出すと、`cancellation_token`を使用して作成されたオブジェクト、 [cancellation_token::none](#none)メソッドです。  
  
## <a name="see-also"></a>関連項目  
 [concurrency 名前空間](concurrency-namespace.md)

