---
title: "ワーカー アーキタイプ |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- Worker archetype
ms.assetid: 834145cd-09d3-4149-bc99-620e1871cbfb
caps.latest.revision: 16
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
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: 046160644cca3bd23e4293a3c52692d2b4c94cd5
ms.lasthandoff: 02/24/2017

---
# <a name="worker-archetype"></a>ワーカーのアーキタイプ
準拠するクラス、*ワーカー*アーキタイプがスレッド プールのキューに作業アイテムを処理するコードを提供します。  
  
 **実装**  
  
 この原型に準拠するクラスを実装するには、クラスは、次の機能を用意する必要があります。  
  
|メソッド|説明|  
|------------|-----------------|  
|[初期化します。](#initialize)|すべての要求が渡される前に、ワーカー オブジェクトを初期化するためと呼ばれる[Execute](#execute)します。|  
|[実行します。](#execute)|作業項目の処理と呼ばれます。|  
|[終了](#terminate)|ワーカー オブジェクトの初期化解除に渡されたすべての要求後に呼び出された[Execute](#execute)します。|  
  
|Typedef|説明|  
|-------------|-----------------|  
|[RequestType](#requesttype)|ワーカー クラスによって処理できる作業項目の種類の typedef。|  
  
 標準的な*ワーカー*クラスは、次のようになります。  
  
 [!code-cpp[NVC_ATL_Utilities #&137;](../../atl/codesnippet/cpp/worker-archetype_1.cpp)]  
  
 **既存の実装**  
  
 これらのクラスは、この原型に準拠します。  
  
|クラス|説明|  
|-----------|-----------------|  
|[CNonStatelessWorker](../../atl/reference/cnonstatelessworker-class.md)|スレッド プールからの要求を受信し、作成され、要求ごとに破棄する worker オブジェクトにメッセージを渡します。|  
  
 **使用します。**  
  
 これらのテンプレート パラメーターには、この原型に準拠するようにクラスが期待される結果します。  
  
|パラメーター名|使用者|  
|--------------------|-------------|  
|*作業者*|[CThreadPool](../../atl/reference/cthreadpool-class.md)|  
|*作業者*|[CNonStatelessWorker](../../atl/reference/cnonstatelessworker-class.md)|  
  
### <a name="requirements"></a>要件  
 **ヘッダー:** atlutil.h  
  
## <a name="a-nameexecuteaworkerarchetypeexecute"></a><a name="execute"></a>WorkerArchetype::Execute
作業項目の処理と呼ばれます。  
  
  
  
```  
void Execute(
    RequestType request,  
    void* pvWorkerParam,  
    OVERLAPPED* pOverlapped);
```  
  
#### <a name="parameters"></a>パラメーター  
 `request`  
 処理する作業アイテム。 作業項目のと同じ型が`RequestType`です。  
  
 `pvWorkerParam`  
 Worker クラスで認識されるカスタム パラメーターです。 渡されるも`WorkerArchetype::Initialize`と`Terminate`です。  
  
 `pOverlapped`  
 ポインター、 [OVERLAPPED](http://msdn.microsoft.com/library/windows/desktop/ms684342)構造体のキューに置かれた項目関連する作業のキューを作成するために使用します。  
  
## <a name="a-nameinitializea-workerarchetypeinitialize"></a><a name="initialize"></a>WorkerArchetype::Initialize
すべての要求が渡される前に、ワーカー オブジェクトを初期化するためと呼ばれる`WorkerArchetype::Execute`です。  
```
BOOL Initialize(void* pvParam) throw();
```  
  
#### <a name="parameters"></a>パラメーター  
 `pvParam`  
 Worker クラスで認識されるカスタム パラメーターです。 渡されるも`WorkerArchetype::Terminate`と`WorkerArchetype::Execute`です。  
  
### <a name="return-value"></a>戻り値  
 返す**TRUE**成功した場合、 **FALSE**失敗します。  
  
## <a name="a-namerequesttypea-workerarchetyperequesttype"></a><a name="requesttype"></a>WorkerArchetype::RequestType
ワーカー クラスによって処理できる作業項目の種類の typedef。  
  
```  
typedef MyRequestType RequestType;    
```  
  
### <a name="remarks"></a>コメント  
 この型は、の最初のパラメーターとして使用する必要があります`WorkerArchetype::Execute`ULONG_PTR との間にキャストできる必要があるとします。  
  
## <a name="a-nameterminatea-workerarchetypeterminate"></a><a name="terminate"></a>WorkerArchetype::Terminate
ワーカー オブジェクトの初期化解除に渡されたすべての要求後に呼び出された`WorkerArchetype::Execute`)。  
    
``` 
void Terminate(void* pvParam) throw();
```  
  
#### <a name="parameters"></a>パラメーター  
 `pvParam`  
 Worker クラスで認識されるカスタム パラメーターです。 渡されるも`WorkerArchetype::Initialize`と`WorkerArchetype::Execute`です。  
  
## <a name="see-also"></a>関連項目  
 [Archetypes」](../../atl/reference/atl-archetypes.md)   
 [概念](../../atl/active-template-library-atl-concepts.md)   
 [ATL COM デスクトップ コンポーネント](../../atl/atl-com-desktop-components.md)




