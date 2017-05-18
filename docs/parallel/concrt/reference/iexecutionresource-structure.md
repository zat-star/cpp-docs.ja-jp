---
title: "IExecutionResource 構造体 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- IExecutionResource
- CONCRTRM/concurrency::IExecutionResource
- CONCRTRM/concurrency::IExecutionResource::IExecutionResource::CurrentSubscriptionLevel
- CONCRTRM/concurrency::IExecutionResource::IExecutionResource::GetExecutionResourceId
- CONCRTRM/concurrency::IExecutionResource::IExecutionResource::GetNodeId
- CONCRTRM/concurrency::IExecutionResource::IExecutionResource::Remove
dev_langs:
- C++
helpviewer_keywords:
- IExecutionResource structure
ms.assetid: 6b27042b-b98c-4f7f-b831-566950af84cd
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 5faef5bd1be6cc02d6614a6f6193c74167a8ff23
ms.openlocfilehash: fa3c65780ac9e001e6f6b8a015dc7f70df47181f
ms.contentlocale: ja-jp
ms.lasthandoff: 03/17/2017

---
# <a name="iexecutionresource-structure"></a>IExecutionResource 構造体
ハードウェア スレッドの抽象化です。  
  
## <a name="syntax"></a>構文  
  
```
struct IExecutionResource;
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[Iexecutionresource::currentsubscriptionlevel](#currentsubscriptionlevel)|アクティブ化された仮想プロセッサの数は、ルートし、この実行リソースが表す基になるハードウェア スレッドに関連付けられている外部のスレッドを購読を返します。|  
|[Iexecutionresource::getexecutionresourceid](#getexecutionresourceid)|この実行リソースを表すハードウェア スレッドの一意の識別子を返します。|  
|[Iexecutionresource::getnodeid](#getnodeid)|この実行リソースが属するプロセッサ ノードの一意の識別子を返します。|  
|[Iexecutionresource::remove](#remove)|この実行リソースをリソース マネージャーを返します。|  
  
## <a name="remarks"></a>コメント  
 実行リソースはスタンドアロンでまたは仮想プロセッサ ルートに関連付けられています。 アプリケーションのスレッドがスレッドのサブスクリプションを作成するときは、スタンドアロンの実行リソースが作成されます。 メソッド[ISchedulerProxy::SubscribeThread](ischedulerproxy-structure.md#subscribecurrentthread)と[ischedulerproxy::requestinitialvirtualprocessors](ischedulerproxy-structure.md#requestinitialvirtualprocessors)スレッドのサブスクリプションを作成して返す、`IExecutionResource`サブスクリプションを表すインターフェイスです。 スレッドのサブスクリプションを作成すると、特定のスレッドが作業に参加するリソース マネージャーに通知する方法は、リソース マネージャーが、スケジューラに割り当てる仮想プロセッサ ルートと、スケジューラにキューに置かれたです。 リソース マネージャーは、可能ハードウェア スレッドの規定量を超えるように情報を使用します。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 `IExecutionResource`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** concrtrm.h  
  
 **名前空間:** concurrency  
  
##  <a name="currentsubscriptionlevel"></a>Iexecutionresource::currentsubscriptionlevel メソッド  
 アクティブ化された仮想プロセッサの数は、ルートし、この実行リソースが表す基になるハードウェア スレッドに関連付けられている外部のスレッドを購読を返します。  
  
```
virtual unsigned int CurrentSubscriptionLevel() const = 0;
```  
  
### <a name="return-value"></a>戻り値  
 現在のサブスクリプション レベルです。  
  
### <a name="remarks"></a>コメント  
 サブスクリプション レベルには、実行中のスレッドの数がハードウェア スレッドに関連付けられたが示しています。 これには、リソース マネージャーは、サブスクライブしているスレッドとスレッド プロキシをアクティブに実行している仮想プロセッサ ルートの形式を認識してスレッドにはのみが含まれます。  
  
 メソッドを呼び出す[ischedulerproxy::subscribecurrentthread](ischedulerproxy-structure.md#subscribecurrentthread)、またはメソッド[ischedulerproxy::requestinitialvirtualprocessors](ischedulerproxy-structure.md#requestinitialvirtualprocessors)パラメーターと共に`doSubscribeCurrentThread`値に設定`true`ハードウェア スレッドのサブスクリプション レベルを&1; つ増やします。 返すことも、`IExecutionResource`サブスクリプションを表すインターフェイスです。 対応する呼び出し、 [iexecutionresource::remove](#remove)デクリメント ハードウェア スレッドのサブスクリプション レベルを&1; つです。  
  
 メソッドを使用して仮想プロセッサ ルートをアクティブ化する[ivirtualprocessorroot::activate](ivirtualprocessorroot-structure.md#activate)ハードウェア スレッドのサブスクリプション レベルを&1; ずつインクリメントされます。 メソッド[ivirtualprocessorroot::deactivate](ivirtualprocessorroot-structure.md#deactivate)、または[iexecutionresource::remove](#remove)サブスクリプション レベルをアクティブ化された仮想プロセッサ ルートで呼び出されたときに&1; つだけデクリメントします。  
  
 リソース マネージャーは、スケジューラ間でリソースを移動するかを判断する方法の&1; つとして、サブスクリプション レベルの情報を使用します。  
  
##  <a name="getexecutionresourceid"></a>Iexecutionresource::getexecutionresourceid メソッド  
 この実行リソースを表すハードウェア スレッドの一意の識別子を返します。  
  
```
virtual unsigned int GetExecutionResourceId() const = 0;
```  
  
### <a name="return-value"></a>戻り値  
 この実行リソースを基になるハードウェア スレッドの一意の識別子。  
  
### <a name="remarks"></a>コメント  
 各ハードウェア スレッドには、同時実行ランタイムによって一意の識別子が割り当てられます。 複数の実行リソースが関連付けられているハードウェアである場合、スレッド、すべてが同じ実行リソース識別子。  
  
##  <a name="getnodeid"></a>Iexecutionresource::getnodeid メソッド  
 この実行リソースが属するプロセッサ ノードの一意の識別子を返します。  
  
```
virtual unsigned int GetNodeId() const = 0;
```  
  
### <a name="return-value"></a>戻り値  
 プロセッサ ノードの一意の識別子。  
  
### <a name="remarks"></a>コメント  
 同時実行ランタイムでは、プロセッサ ノードのグループでは、システム上のハードウェア スレッドを表します。 通常、ノードは、システムのハードウェア トポロジから派生します。 たとえば、特定のソケットまたは特定の NUMA ノードのすべてのプロセッサが同一プロセッサ ノードに属している可能性があります。 リソース マネージャーでは、以降でこれらのノードに一意の識別子を割り当てます`0`含む`nodeCount - 1`ここで、`nodeCount`システム上のプロセッサ ノードの合計数を表します。  
  
 関数からのノードの数を取得できます[GetProcessorNodeCount](concurrency-namespace-functions.md)します。  
  
##  <a name="remove"></a>Iexecutionresource::remove メソッド  
 この実行リソースをリソース マネージャーを返します。  
  
```
virtual void Remove(_Inout_ IScheduler* pScheduler) = 0;
```  
  
### <a name="parameters"></a>パラメーター  
 `pScheduler`  
 この実行リソースを削除する要求を行っているスケジューラのインターフェイスです。  
  
### <a name="remarks"></a>コメント  
 このメソッドを使用すると、スタンドアロンの実行リソースのほか、仮想プロセッサ ルートをリソース マネージャーに関連付けられている実行リソースを返します。  
  
 いずれかから受信した場合、これは、スタンドアロンの実行リソース[ischedulerproxy::subscribecurrentthread](ischedulerproxy-structure.md#subscribecurrentthread)または[ischedulerproxy::requestinitialvirtualprocessors](ischedulerproxy-structure.md#requestinitialvirtualprocessors)、メソッドを呼び出す`Remove`にリソースが作成されたスレッドのサブスクリプションが終了を表します。 スケジューラのプロキシをシャット ダウンする前にすべてのスレッドのサブスクリプションを終了するために必要なして呼び出す必要があります`Remove`サブスクリプションを作成したスレッドからです。  
  
 仮想プロセッサ ルートも、返されるリソース マネージャーを呼び出して、`Remove`メソッド、ためインターフェイス`IVirtualProcessorRoot`から継承、`IExecutionResource`インターフェイスです。 呼び出しに応答のいずれかの仮想プロセッサ ルートを返す必要があります、 [ischeduler::removevirtualprocessors](ischeduler-structure.md#removevirtualprocessors)メソッド、またはから取得したオーバーサブスク ライブ仮想プロセッサ ルートが完了したときに、 [ischedulerproxy::createoversubscriber](ischedulerproxy-structure.md#createoversubscriber)メソッドです。 仮想プロセッサ ルートの制限がないスレッドを呼び出すことができる、`Remove`メソッドです。  
  
 `invalid_argument`場合にスローされますが、パラメーター`pScheduler`に設定されている`NULL`します。  
  
 `invalid_operation`場合にスローされますが、パラメーター`pScheduler`とは異なる、スケジューラ、または、スタンドアロンの実行リソースでは、この実行リソースが作成されたこと、現在のスレッドがスレッドのサブスクリプションを作成したスレッドと異なる場合です。  
  
## <a name="see-also"></a>関連項目  
 [同時実行 Namespace](concurrency-namespace.md)   
 [IVirtualProcessorRoot 構造体](ivirtualprocessorroot-structure.md)

