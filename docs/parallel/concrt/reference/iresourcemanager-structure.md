---
title: "IResourceManager 構造体 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- IResourceManager
- CONCRTRM/concurrency::IResourceManager
- CONCRTRM/concurrency::IResourceManager::IResourceManager::OSVersion
- CONCRTRM/concurrency::IResourceManager::IResourceManager::CreateNodeTopology
- CONCRTRM/concurrency::IResourceManager::IResourceManager::GetAvailableNodeCount
- CONCRTRM/concurrency::IResourceManager::IResourceManager::GetFirstNode
- CONCRTRM/concurrency::IResourceManager::IResourceManager::Reference
- CONCRTRM/concurrency::IResourceManager::IResourceManager::RegisterScheduler
- CONCRTRM/concurrency::IResourceManager::IResourceManager::Release
dev_langs: C++
helpviewer_keywords: IResourceManager structure
ms.assetid: 3dd5ec2c-fe53-4121-ae77-1bc1d1167ff4
caps.latest.revision: "20"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: ca65d1e021bc1710386bf7b448b55378af96f56e
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="iresourcemanager-structure"></a>IResourceManager 構造体
同時実行ランタイムのリソース マネージャーに対するインターフェイスです。 これは、スケジューラがリソース マネージャーと通信する際に使用されるインターフェイスです。  
  
## <a name="syntax"></a>構文  
  
```
struct IResourceManager;
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-enumerations"></a>パブリック列挙型  
  
|名前|説明|  
|----------|-----------------|  
|[Iresourcemanager::osversion](#osversion)|オペレーティング システムのバージョンを表す列挙型。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[Iresourcemanager::createnodetopology](#createnodetopology)|デバッグにのみ存在がランタイムのビルドをテスト フックをハードウェア トポロジをさまざまな構成に一致する実際のハードウェアを必要とせずにリソース マネージャーのテストを容易にするため、このメソッドはします。 ランタイムの製品版ビルドでは、このメソッドは操作を実行せずに戻ります。|  
|[Iresourcemanager::getavailablenodecount](#getavailablenodecount)|リソース マネージャーを使用可能なノードの数を返します。|  
|[Iresourcemanager::getfirstnode](#getfirstnode)|リソース マネージャーで定義される、列挙の順番に最初のノードを返します。|  
|[Iresourcemanager::reference](#reference)|リソース マネージャー インスタンスの参照カウントをインクリメントします。|  
|[Iresourcemanager::registerscheduler](#registerscheduler)|リソース マネージャーと、スケジューラに登録します。 スケジューラが登録されるを使用して、リソース マネージャーと通信する必要があります、`ISchedulerProxy`返されるインターフェイスです。|  
|[Iresourcemanager::release](#release)|リソース マネージャー インスタンスで、参照カウントをデクリメントします。 リソース マネージャーが破棄されるは、参照カウントになると`0`です。|  
  
## <a name="remarks"></a>コメント  
 使用して、 [CreateResourceManager](concurrency-namespace-functions.md)シングルトン リソース マネージャー インスタンスへのインターフェイスを取得します。 メソッドは、リソース マネージャーの参照カウントをインクリメントし、呼び出す必要がある、 [iresourcemanager::release](#release)リソース マネージャーと共にが完了したら、参照を解放します。 通常、各スケジューラを作成するは、作成中に、このメソッドを呼び出すし、参照を解放する、リソース マネージャーをシャット ダウン後。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 `IResourceManager`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** concrtrm.h  
  
 **名前空間:** concurrency  
  
##  <a name="createnodetopology"></a>Iresourcemanager::createnodetopology メソッド  
 デバッグにのみ存在がランタイムのビルドをテスト フックをハードウェア トポロジをさまざまな構成に一致する実際のハードウェアを必要とせずにリソース マネージャーのテストを容易にするため、このメソッドはします。 ランタイムの製品版ビルドでは、このメソッドは操作を実行せずに戻ります。  
  
```
virtual void CreateNodeTopology(
    unsigned int nodeCount,
    _In_reads_(nodeCount) unsigned int* pCoreCount,
    _In_reads_opt_(nodeCount) unsigned int** pNodeDistance,
    _In_reads_(nodeCount) unsigned int* pProcessorGroups) = 0;
```  
  
### <a name="parameters"></a>パラメーター  
 `nodeCount`  
 シミュレートされたプロセッサのノードの数。  
  
 `pCoreCount`  
 各ノードのコアの数を指定する配列。  
  
 `pNodeDistance`  
 2 つのノード間の距離を指定する行列。 このパラメーターは、値を持つこと`NULL`です。  
  
 `pProcessorGroups`  
 プロセッサ グループを指定する配列の各ノードに属しています。  
  
### <a name="remarks"></a>コメント  
 [invalid_argument](../../../standard-library/invalid-argument-class.md)場合にスローされるパラメーター`nodeCount`プロパティ値を持つ`0`が渡され、またはパラメーター`pCoreCount`プロパティ値を持つ`NULL`します。  
  
 [invalid_operation](invalid-operation-class.md)が、他のスケジューラが、プロセスに存在していて、このメソッドが呼び出された場合にスローされます。  
  
##  <a name="getavailablenodecount"></a>Iresourcemanager::getavailablenodecount メソッド  
 リソース マネージャーを使用可能なノードの数を返します。  
  
```
virtual unsigned int GetAvailableNodeCount() const = 0;
```  
  
### <a name="return-value"></a>戻り値  
 リソース マネージャーを使用可能なノードの数。  
  
##  <a name="getfirstnode"></a>Iresourcemanager::getfirstnode メソッド  
 リソース マネージャーで定義される、列挙の順番に最初のノードを返します。  
  
```
virtual ITopologyNode* GetFirstNode() const = 0;
```  
  
### <a name="return-value"></a>戻り値  
 リソース マネージャーで定義される列挙の順番に最初のノードです。  
  
##  <a name="iresourcemanager__osversion"></a>Iresourcemanager::osversion 列挙  
 オペレーティング システムのバージョンを表す列挙型。  
  
```
enum OSVersion;
```  
  
##  <a name="reference"></a>Iresourcemanager::reference メソッド  
 リソース マネージャー インスタンスの参照カウントをインクリメントします。  
  
```
virtual unsigned int Reference() = 0;
```  
  
### <a name="return-value"></a>戻り値  
 結果として得られる、参照カウントします。  
  
##  <a name="registerscheduler"></a>Iresourcemanager::registerscheduler メソッド  
 リソース マネージャーと、スケジューラに登録します。 スケジューラが登録されるを使用して、リソース マネージャーと通信する必要があります、`ISchedulerProxy`返されるインターフェイスです。  
  
```
virtual ISchedulerProxy *RegisterScheduler(
    _Inout_ IScheduler* pScheduler,
    unsigned int version) = 0;
```  
  
### <a name="parameters"></a>パラメーター  
 `pScheduler`  
 `IScheduler`登録するスケジューラへのインターフェイスです。  
  
 `version`  
 スケジューラがリソース マネージャーとの通信に使用して通信インターフェイスのバージョン。 スケジューラに古い機能のアクセス権を取得しながら、通信インターフェイスを発展させるリソース マネージャーは、バージョンを使用します。 Visual Studio 2010 に存在するリソース マネージャー機能を使用するスケジューラは、バージョンを使用する必要があります`CONCRT_RM_VERSION_1`です。  
  
### <a name="return-value"></a>戻り値  
 `ISchedulerProxy`リソース マネージャーが、スケジューラに関連付けられているインターフェイス。 スケジューラでこのポイントからリソース マネージャーとの通信にこのインターフェイスを使用する必要があります。  
  
### <a name="remarks"></a>コメント  
 リソース マネージャーとの通信を開始するのにには、このメソッドを使用します。 メソッドに関連付けます、`IScheduler`とスケジューラのインターフェイス、`ISchedulerProxy`インターフェイスと、再度手します。 リソース マネージャーとのスレッドをサブスクライブするか、スケジューラが使用する実行リソースを要求する、返されたインターフェイスを使用できます。 リソース マネージャーがによって返される、スケジューラ ポリシーからポリシーの要素を使用して、 [ischeduler::getpolicy](ischeduler-structure.md#getpolicy)スケジューラのスレッドの種類を判断するメソッドは作業を実行する必要があります。 場合、`SchedulerKind`ポリシー キーが値を持つ`UmsThreadDefault`値として、ポリシーから戻さ値を読み取ると`UmsThreadDefault`、`IScheduler`インターフェイス、メソッドに渡す必要があります、`IUMSScheduler`インターフェイスです。  
  
 メソッドをスロー、`invalid_argument`例外場合、パラメーター`pScheduler`プロパティ値を持つ`NULL`場合、またはパラメーター`version`通信インターフェイスの有効なバージョンではありません。  
  
##  <a name="release"></a>Iresourcemanager::release メソッド  
 リソース マネージャー インスタンスで、参照カウントをデクリメントします。 リソース マネージャーが破棄されるは、参照カウントになると`0`です。  
  
```
virtual unsigned int Release() = 0;
```  
  
### <a name="return-value"></a>戻り値  
 結果として得られる、参照カウントします。  
  
## <a name="see-also"></a>関連項目  
 [同時実行 Namespace](concurrency-namespace.md)   
 [ISchedulerProxy 構造体](ischedulerproxy-structure.md)   
 [IScheduler 構造体](ischeduler-structure.md)
