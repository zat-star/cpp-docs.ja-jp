---
title: "scheduler_worker_creation_error クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- concrt/concurrency::scheduler_worker_creation_error
dev_langs:
- C++
helpviewer_keywords:
- scheduler_worker_creation_error class
ms.assetid: 4aec1c3e-c32a-41b2-899d-2d898f23b3c7
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
ms.openlocfilehash: c880ed65ef9e01c7eebdd2de45598a41763da57c
ms.lasthandoff: 02/24/2017

---
# <a name="schedulerworkercreationerror-class"></a>scheduler_worker_creation_error クラス
このクラスは、同時実行ランタイムでワーカー実行コンテキストを作成できないためにスローされる例外を表します。  
  
## <a name="syntax"></a>構文  
  
```
class scheduler_worker_creation_error : public scheduler_resource_allocation_error;
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[scheduler_worker_creation_error コンス トラクター](#ctor)|オーバーロードされます。 `scheduler_worker_creation_error` オブジェクトを構築します。|  
  
## <a name="remarks"></a>コメント  
 同時実行ランタイムの内部から実行コンテキストを作成するには、オペレーティング システムに呼び出しが失敗したときに、この例外はスロー通常。 実行コンテキストは、同時実行ランタイムでタスクを実行するスレッドです。 Win32 メソッドの呼び出しから返されるエラー コード`GetLastError`型の値に変換`HRESULT`と基本クラスのメソッドを使用して取得できる`get_error_code`です。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 `exception`  
  
 [scheduler_resource_allocation_error](scheduler-resource-allocation-error-class.md)  
  
 `scheduler_worker_creation_error`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** concrt.h  
  
 **名前空間:** concurrency  
  
##  <a name="a-namectora-schedulerworkercreationerror"></a><a name="ctor"></a>scheduler_worker_creation_error 

 `scheduler_worker_creation_error` オブジェクトを構築します。  
  
```
scheduler_worker_creation_error(
    _In_z_ const char* _Message,
    HRESULT _Hresult) throw();

explicit _CRTIMP scheduler_worker_creation_error(
    HRESULT _Hresult) throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `_Message`  
 エラーの説明メッセージ。  
  
 `_Hresult`  
 `HRESULT`例外が発生したエラーの値。  
  
## <a name="see-also"></a>関連項目  
 [同時実行 Namespace](concurrency-namespace.md)

