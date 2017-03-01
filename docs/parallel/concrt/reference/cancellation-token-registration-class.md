---
title: "cancellation_token_registration クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- pplcancellation_token/concurrency::cancellation_token_registration
dev_langs:
- C++
helpviewer_keywords:
- cancellation_token_registration class
ms.assetid: 823d63f4-7233-4d65-8976-6152ccf12d0e
caps.latest.revision: 9
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
ms.openlocfilehash: 72c317bb95b646a3a97b361ac3248f015cd0f29a
ms.lasthandoff: 02/24/2017

---
# <a name="cancellationtokenregistration-class"></a>cancellation_token_registration クラス
`cancellation_token_registration` クラスは、`cancellation_token` からのコールバック通知を表します。 `register` の `cancellation_token` メソッドを使用して取り消し発生の通知を受け取るとき、`cancellation_token_registration` オブジェクトはハンドルとしてコールバックに返されます。したがって、呼び出し元は `deregister` メソッドを使用して、特定のコールバックが以降行われないように要求できます。  
  
## <a name="syntax"></a>構文  
  
```
class cancellation_token_registration;
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[cancellation_token_registration コンス トラクター](#ctor)||  
|[~ cancellation_token_registration デストラクター](#dtor)||  
  
### <a name="public-operators"></a>パブリック演算子  
  
|名前|説明|  
|----------|-----------------|  
|[operator! = 演算子](#operator_neq)||  
|[operator = 演算子](#operator_eq)||  
|[operator = 演算子](#operator_eq_eq)||  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 `cancellation_token_registration`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** pplcancellation_token.h  
  
 **名前空間:** concurrency  
  
##  <a name="a-namedtora-cancellationtokenregistration"></a><a name="dtor"></a>~ cancellation_token_registration 

```
~cancellation_token_registration();
```  
  
##  <a name="a-namectora-cancellationtokenregistration"></a><a name="ctor"></a>cancellation_token_registration 

```
cancellation_token_registration();

cancellation_token_registration(const cancellation_token_registration& _Src);

cancellation_token_registration(cancellation_token_registration&& _Src);
```  
  
### <a name="parameters"></a>パラメーター  
 `_Src`  
  
##  <a name="a-nameoperatorneqa-operator"></a><a name="operator_neq"></a>operator! = 

```
bool operator!= (const cancellation_token_registration& _Rhs) const;
```  
  
### <a name="parameters"></a>パラメーター  
 `_Rhs`  
  
### <a name="return-value"></a>戻り値  
  
##  <a name="a-nameoperatoreqa-operator"></a><a name="operator_eq"></a>演算子 = 

```
cancellation_token_registration& operator= (const cancellation_token_registration& _Src);

cancellation_token_registration& operator= (cancellation_token_registration&& _Src);
```  
  
### <a name="parameters"></a>パラメーター  
 `_Src`  
  
### <a name="return-value"></a>戻り値  
  
##  <a name="a-nameoperatoreqeqa-operator"></a><a name="operator_eq_eq"></a>演算子 = = 

```
bool operator== (const cancellation_token_registration& _Rhs) const;
```  
  
### <a name="parameters"></a>パラメーター  
 `_Rhs`  
  
### <a name="return-value"></a>戻り値  
  
## <a name="see-also"></a>関連項目  
 [同時実行 Namespace](concurrency-namespace.md)

