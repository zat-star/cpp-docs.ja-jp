---
title: "scheduler_ptr 構造体 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- pplinterface/concurrency::scheduler_ptr
dev_langs:
- C++
ms.assetid: e88c84af-c306-476d-aef1-f42a0fa0a80f
caps.latest.revision: 8
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
ms.sourcegitcommit: fa774c7f025b581d65c28d65d83e22ff2d798230
ms.openlocfilehash: 022b5fafc437a8103fe17967a9a5ea54d5b82a39
ms.lasthandoff: 02/24/2017

---
# <a name="schedulerptr-structure"></a>scheduler_ptr 構造体
スケジューラへのポインターを表します。 このクラスによって、shared_ptr を使用して共有有効期間を指定できるように、または、生ポインターを使用して参照できるようにします。  
  
## <a name="syntax"></a>構文  
  
```
struct scheduler_ptr;
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[scheduler_ptr::scheduler_ptr コンス トラクター](#ctor)|オーバーロードされます。 shared_ptr からスケジューラを指すスケジューラ ポインターを作成します。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[scheduler_ptr::get メソッド](#get)|スケジューラへの生のポインターを返します。|  
  
### <a name="public-operators"></a>パブリック演算子  
  
|名前|説明|  
|----------|-----------------|  
|[scheduler_ptr::operator bool 演算子](#operator_bool)|スケジューラ ポインターが null 以外であるかどうかをテストします。|  
|[scheduler_ptr::operator-&gt;演算子](#operator_ptr)|ポインターのように動作します。|  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 `scheduler_ptr`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** pplinterface.h  
  
 **名前空間:** concurrency  
  
##  <a name="a-namegeta--schedulerptrget-method"></a><a name="get"></a>scheduler_ptr::get メソッド  
 スケジューラへの生のポインターを返します。  
  
```
scheduler_interface* get() const;
```  
  
### <a name="return-value"></a>戻り値  
  
##  <a name="a-nameoperatorboola--schedulerptroperator-bool"></a><a name="operator_bool"></a>scheduler_ptr::operator bool   
 スケジューラ ポインターが null 以外であるかどうかをテストします。  
  
'' 演算子 bool() const です。
```  
  
##  <a name="operator_ptr"></a>  scheduler_ptr::operator-&gt;   
 Behave like a pointer  
  
```
scheduler_interface * operator->() const です。
```  
  
### Return Value  
  
##  <a name="ctor"></a>  scheduler_ptr::scheduler_ptr Constructor  
 Creates a scheduler pointer from shared_ptr to scheduler  
  
```
明示的な scheduler_ptr(std::shared_ptr<scheduler_interface> scheduler);</scheduler_interface>

明示的な scheduler_ptr (_In_opt_ scheduler_interface * pScheduler) です。
```  
  
### Parameters  
 `scheduler`  
 `pScheduler`  
  
## See Also  
 [concurrency Namespace](concurrency-namespace.md)

