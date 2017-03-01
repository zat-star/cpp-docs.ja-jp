---
title: "scheduler_resource_allocation_error クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- concrt/concurrency::scheduler_resource_allocation_error
dev_langs:
- C++
helpviewer_keywords:
- scheduler_resource_allocation_error class
ms.assetid: 8b40449a-7abb-4d0a-bb85-c0e9a495ae97
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
ms.sourcegitcommit: fc190feb08d9b221cd1cc21a9c91ad567c86c848
ms.openlocfilehash: 52233a99e1d1a715fc7d52599ffeff18a3c2c34b
ms.lasthandoff: 02/24/2017

---
# <a name="schedulerresourceallocationerror-class"></a>scheduler_resource_allocation_error クラス
このクラスは、同時実行ランタイムでクリティカル リソースを取得できないためにスローされる例外を表します。  
  
## <a name="syntax"></a>構文  
  
```
class scheduler_resource_allocation_error : public std::exception;
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[scheduler_resource_allocation_error コンス トラクター](#ctor)|オーバーロードされます。 `scheduler_resource_allocation_error` オブジェクトを構築します。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[get_error_code メソッド](#get_error_code)|例外が発生したエラー コードを返します。|  
  
## <a name="remarks"></a>コメント  
 同時実行ランタイムの内部からオペレーティング システムへの呼び出しが失敗した場合、この例外はスロー通常。 Win32 メソッドの呼び出しから返されるエラー コード`GetLastError`型の値に変換`HRESULT`とを使用して取得できる、`get_error_code`メソッドです。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 `exception`  
  
 `scheduler_resource_allocation_error`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** concrt.h  
  
 **名前空間:** concurrency  
  
##  <a name="a-namegeterrorcodea-geterrorcode"></a><a name="get_error_code"></a>get_error_code 

 例外が発生したエラー コードを返します。  
  
```
HRESULT get_error_code() const throw();
```  
  
### <a name="return-value"></a>戻り値  
 `HRESULT`例外が発生したエラーの値。  
  
##  <a name="a-namectora-schedulerresourceallocationerror"></a><a name="ctor"></a>scheduler_resource_allocation_error 

 `scheduler_resource_allocation_error` オブジェクトを構築します。  
  
```
scheduler_resource_allocation_error(
    _In_z_ const char* _Message,
    HRESULT _Hresult) throw();

explicit _CRTIMP scheduler_resource_allocation_error(
    HRESULT _Hresult) throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `_Message`  
 エラーの説明メッセージ。  
  
 `_Hresult`  
 `HRESULT`例外が発生したエラーの値。  
  
## <a name="see-also"></a>関連項目  
 [同時実行 Namespace](concurrency-namespace.md)

