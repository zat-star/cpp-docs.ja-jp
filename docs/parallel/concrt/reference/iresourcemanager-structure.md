---
title: "IResourceManager 構造体 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
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
dev_langs:
- C++
helpviewer_keywords:
- IResourceManager structure
ms.assetid: 3dd5ec2c-fe53-4121-ae77-1bc1d1167ff4
caps.latest.revision: 20
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
ms.openlocfilehash: 2d054bd632db90708d90fe8d791965b47f713493
ms.contentlocale: ja-jp
ms.lasthandoff: 03/17/2017

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
|[Iresourcemanager::createnodetopology](#createnodetopology)|ランタイムのビルド時にデバッグにのみ存在で、このメソッドはテスト フックをハードウェア トポロジをさまざまな構成に一致する実際のハードウェアを必要とせずにリソース マネージャーのテストを容易にするためです。 ランタイムの製品版ビルドでは、このメソッドは操作を実行せずに戻ります。|  
|[Iresourcemanager::getavailablenodecount](#getavailablenodecount)|リソース マネージャーを使用可能なノードの数を返します。|  
|[Iresourcemanager::getfirstnode](#getfirstnode)|リソース マネージャーで定義される、列挙の順番に最初のノードを返します。|  
|[Iresourcemanager::reference](#reference)|リソース マネージャーのインスタンスの参照カウントをインクリメントします。|  
|[Iresourcemanager::registerscheduler](#registerscheduler)|リソース マネージャーで、スケジューラに登録します。 スケジューラが登録されるを使用して、リソース マネージャーと通信する必要があります、`ISchedulerProxy`返されるインターフェイスです。|  
|[Iresourcemanager::release](#release)|リソース マネージャーのインスタンスで、参照カウントをデクリメントします。 リソース マネージャーが破棄されるは、参照カウントが`0`です。|  
  
## <a name="remarks"></a>コメント  
 使用して、 [CreateResourceManager](concurrency-namespace-functions.md)シングルトン リソース マネージャーのインスタンスへのインターフェイスを取得します。 メソッドは、リソース マネージャーの参照カウントをインクリメントし、呼び出す必要があります、 [iresourcemanager::release](#release)したらリソース マネージャーでの参照を解放します。 通常、各スケジューラを作成するはの作成時に、このメソッドを呼び出すし、シャット ダウン後に、リソース マネージャーへの参照を解放します。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 `IResourceManager`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** concrtrm.h  
  
 **名前空間:** concurrency  
  
##  <a name="createnodetopology"></a>Iresourcemanager::createnodetopology メソッド  
 ランタイムのビルド時にデバッグにのみ存在で、このメソッドはテスト フックをハードウェア トポロジをさまざまな構成に一致する実際のハードウェアを必要とせずにリソース マネージャーのテストを容易にするためです。 ランタイムの製品版ビルドでは、このメソッドは操作を実行せずに戻ります。  
  
```
virtual void CreateNodeTopology(
    unsigned int nodeCount,
    _In_reads_(nodeCount) unsigned int* pCoreCount,
    _In_reads_opt_(nodeCount) unsigned int** pNodeDistance,
    _In_reads_(nodeCount) unsigned int* pProcessorGroups) = 0;
```  
  
### <a name="parameters"></a>パラメーター  
 `nodeCount`  
 シミュレートされたプロセッサ ノードの数。  
  
 `pCoreCount`  
 各ノードのコアの数を指定する配列。  
  
 `pNodeDistance`  
 2 つのノード間の距離を指定する行列。 このパラメーターは、値を持つこと`NULL`します。  
  
 `pProcessorGroups`  
 各ノードが属するプロセッサ グループを指定する配列。  
  
### <a name="remarks"></a>コメント  
 [invalid_argument](../../../standard-library/invalid-argument-class.md)場合にスローされるパラメーター`nodeCount`プロパティ値を持つ`0`が渡され、またはパラメーター`pCoreCount`プロパティ値を持つ`NULL`です。  
  
 [invalid_operation](invalid-operation-class.md)プロセスの他のスケジューラが存在している間、このメソッドが呼び出された場合にスローされます。  
  
##  <a name="getavailablenodecount"></a>Iresourcemanager::getavailablenodecount メソッド  
 リソース マネージャーを使用可能なノードの数を返します。  
  
```
virtual unsigned int GetAvailableNodeCount() const = 0;
```  
  
### <a name="return-value"></a>戻り値  
 リソース マネージャーで利用できるノードの数。  
  
##  <a name="getfirstnode"></a>Iresourcemanager::getfirstnode メソッド  
 リソース マネージャーで定義される、列挙の順番に最初のノードを返します。  
  
```
virtual ITopologyNode* GetFirstNode() const = 0;
```  
  
### <a name="return-value"></a>戻り値  
 リソース マネージャーで定義される列挙の順番に最初のノード。  
  
##  <a name="iresourcemanager__osversion"></a>Iresourcemanager::osversion 列挙  
 オペレーティング システムのバージョンを表す列挙型。  
  
```
enum OSVersion;
```  
  
##  <a name="reference"></a>Iresourcemanager::reference メソッド  
 リソース マネージャーのインスタンスの参照カウントをインクリメントします。  
  
```
virtual unsigned int Reference() = 0;
```  
  
### <a name="return-value"></a>戻り値  
 結果の参照をカウントします。  
  
##  <a name="registerscheduler"></a>Iresourcemanager::registerscheduler メソッド  
 リソース マネージャーで、スケジューラに登録します。 スケジューラが登録されるを使用して、リソース マネージャーと通信する必要があります、`ISchedulerProxy`返されるインターフェイスです。  
  
```
virtual ISchedulerProxy *RegisterScheduler(
    _Inout_ IScheduler* pScheduler,
    unsigned int version) = 0;
```  
  
### <a name="parameters"></a>パラメーター  
 `pScheduler`  
 `IScheduler`に登録するスケジューラへのインターフェイスです。  
  
 `version`  
 通信インターフェイスのバージョン、スケジューラがリソース マネージャーと通信するを使用しています。 バージョンを使用すると、スケジューラに古い機能のアクセス権を取得しながら、通信インターフェイスを進化させるリソース マネージャーができます。 Visual Studio 2010 には存在するリソース マネージャー機能を使用するスケジューラは、バージョンを使用する必要があります`CONCRT_RM_VERSION_1`します。  
  
### <a name="return-value"></a>戻り値  
 `ISchedulerProxy`リソース マネージャーが、スケジューラに関連付けられているインターフェイス。 スケジューラは、このインターフェイスを使用して、この時点でのリソース マネージャーとの通信にする必要があります。  
  
### <a name="remarks"></a>コメント  
 リソース マネージャーとの通信を開始するのにには、このメソッドを使用します。 メソッドに関連付けます、`IScheduler`とスケジューラのインターフェイス、`ISchedulerProxy`インターフェイスと手にして戻します。 スケジューラが使用する実行リソースを要求する、またはリソース マネージャーでのスレッドを購読するは、返されたインターフェイスを使用できます。 リソース マネージャーがポリシーによって返されるスケジューラ ポリシーからの要素を使用して、 [ischeduler::getpolicy](ischeduler-structure.md#getpolicy)スケジューラのスレッドの種類を決定する方法は処理を実行する必要があります。 場合、`SchedulerKind`ポリシー キー プロパティ値を持つ`UmsThreadDefault`値として、ポリシーから戻り値が読み取られると`UmsThreadDefault`、`IScheduler`インターフェイスのメソッドに渡す必要があります、`IUMSScheduler`インターフェイスです。  
  
 メソッドをスロー、`invalid_argument`例外場合、パラメーター`pScheduler`プロパティ値を持つ`NULL`場合は、パラメーター`version`通信インターフェイスの有効なバージョンではありません。  
  
##  <a name="release"></a>Iresourcemanager::release メソッド  
 リソース マネージャーのインスタンスで、参照カウントをデクリメントします。 リソース マネージャーが破棄されるは、参照カウントが`0`です。  
  
```
virtual unsigned int Release() = 0;
```  
  
### <a name="return-value"></a>戻り値  
 結果の参照をカウントします。  
  
## <a name="see-also"></a>関連項目  
 [同時実行 Namespace](concurrency-namespace.md)   
 [ISchedulerProxy 構造体](ischedulerproxy-structure.md)   
 [IScheduler 構造体](ischeduler-structure.md)

