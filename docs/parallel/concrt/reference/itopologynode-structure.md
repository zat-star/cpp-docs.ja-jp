---
title: "ITopologyNode 構造体 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- concrtrm/concurrency::ITopologyNode
dev_langs:
- C++
helpviewer_keywords:
- ITopologyNode structure
ms.assetid: 92e7e032-04f6-4c7c-be36-8f9a35fc4734
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
translationtype: Machine Translation
ms.sourcegitcommit: fa774c7f025b581d65c28d65d83e22ff2d798230
ms.openlocfilehash: 8274da148f9f74cad73d63363bbbaff307943539
ms.lasthandoff: 02/24/2017

---
# <a name="itopologynode-structure"></a>ITopologyNode 構造体
リソース マネージャーで定義されるトポロジ ノードへのインターフェイスです。 ノードには&1; つ以上の実行リソースが含まれます。  
  
## <a name="syntax"></a>構文  
  
```
struct ITopologyNode;
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[Itopologynode::getexecutionresourcecount メソッド](#getexecutionresourcecount)|このノードでグループ化の実行リソースの数を返します。|  
|[Itopologynode::getfirstexecutionresource メソッド](#getfirstexecutionresource)|列挙の順番にこのノードの下にグループ化された最初の実行リソースが返されます。|  
|[Itopologynode::getid メソッド](#getid)|このノードのリソース マネージャーの一意の識別子を返します。|  
|[Itopologynode::getnext メソッド](#getnext)|列挙の順番に次のトポロジのノードにインターフェイスを返します。|  
|[Itopologynode::getnumanode メソッド](#getnumanode)|Windows が割り当てた、このリソース マネージャー ノードが属する、NUMA ノードの数を返します。|  
  
## <a name="remarks"></a>コメント  
 このインターフェイスは、リソース マネージャーで見られるように、システムのトポロジーを順番に通常使用されます。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 `ITopologyNode`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** concrtrm.h  
  
 **名前空間:** concurrency  
  
##  <a name="a-namegetexecutionresourcecounta--itopologynodegetexecutionresourcecount-method"></a><a name="getexecutionresourcecount"></a>Itopologynode::getexecutionresourcecount メソッド  
 このノードでグループ化の実行リソースの数を返します。  
  
```
virtual unsigned int GetExecutionResourceCount() const = 0;
```  
  
### <a name="return-value"></a>戻り値  
 このノードの下の実行リソースの数がグループ化されます。  
  
##  <a name="a-namegetfirstexecutionresourcea--itopologynodegetfirstexecutionresource-method"></a><a name="getfirstexecutionresource"></a>Itopologynode::getfirstexecutionresource メソッド  
 列挙の順番にこのノードの下にグループ化された最初の実行リソースが返されます。  
  
```
virtual ITopologyExecutionResource *GetFirstExecutionResource() const = 0;
```  
  
### <a name="return-value"></a>戻り値  
 列挙の順番にこのノードの下に最初の実行リソースがグループ化されます。  
  
##  <a name="a-namegetida--itopologynodegetid-method"></a><a name="getid"></a>Itopologynode::getid メソッド  
 このノードのリソース マネージャーの一意の識別子を返します。  
  
```
virtual unsigned int GetId() const = 0;
```  
  
### <a name="return-value"></a>戻り値  
 このノードのリソース マネージャーの一意の識別子。  
  
### <a name="remarks"></a>コメント  
 同時実行ランタイムでは、プロセッサ ノードのグループでは、システム上のハードウェア スレッドを表します。 通常、ノードは、システムのハードウェア トポロジから派生します。 たとえば、特定のソケットまたは特定の NUMA ノードのすべてのプロセッサが同一プロセッサ ノードに属している可能性があります。 リソース マネージャーでは、以降でこれらのノードに一意の識別子を割り当てます`0`含む`nodeCount - 1`ここで、`nodeCount`システム上のプロセッサ ノードの合計数を表します。  
  
 関数からのノードの数を取得できます[GetProcessorNodeCount](concurrency-namespace-functions.md)します。  
  
##  <a name="a-namegetnexta--itopologynodegetnext-method"></a><a name="getnext"></a>Itopologynode::getnext メソッド  
 列挙の順番に次のトポロジのノードにインターフェイスを返します。  
  
```
virtual ITopologyNode *GetNext() const = 0;
```  
  
### <a name="return-value"></a>戻り値  
 列挙の順番に次のノードのインターフェイスです。 このメソッドが値を返すシステム トポロジの列挙の順番にノードがそれ以上がある場合は、`NULL`です。  
  
##  <a name="a-namegetnumanodea--itopologynodegetnumanode-method"></a><a name="getnumanode"></a>Itopologynode::getnumanode メソッド  
 Windows が割り当てた、このリソース マネージャー ノードが属する、NUMA ノードの数を返します。  
  
```
virtual unsigned long GetNumaNode() const = 0;
```  
  
### <a name="return-value"></a>戻り値  
 Windows が割り当てた、このリソース マネージャー ノードが属する、NUMA ノードの数。  
  
### <a name="remarks"></a>コメント  
 このノードに属する仮想プロセッサ ルートで実行中のスレッド プロキシは、このメソッドが返す NUMA ノードに、少なくとも NUMA ノードのレベルで関係があります。  
  
## <a name="see-also"></a>関連項目  
 [同時実行 Namespace](concurrency-namespace.md)

