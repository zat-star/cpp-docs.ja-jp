---
title: "ITopologyExecutionResource 構造体 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- ITopologyExecutionResource
- CONCRTRM/concurrency::ITopologyExecutionResource
- CONCRTRM/concurrency::ITopologyExecutionResource::ITopologyExecutionResource::GetId
- CONCRTRM/concurrency::ITopologyExecutionResource::ITopologyExecutionResource::GetNext
dev_langs: C++
helpviewer_keywords: ITopologyExecutionResource structure
ms.assetid: e36756f7-4cd9-4fa6-ba60-23fea58ef2bf
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: caf2cc77cd31df611f71d07c5a0a49f600767f81
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="itopologyexecutionresource-structure"></a>ITopologyExecutionResource 構造体
リソース マネージャーで定義される実行リソースへのインターフェイスです。  
  
## <a name="syntax"></a>構文  
  
```
struct ITopologyExecutionResource;
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[Itopologyexecutionresource::getid](#getid)|この実行リソースのリソース マネージャーの一意の識別子を返します。|  
|[Itopologyexecutionresource::getnext](#getnext)|列挙の順番に次の実行リソースへのインターフェイスを返します。|  
  
## <a name="remarks"></a>コメント  
 このインターフェイスは、通常使用率が低いリソース マネージャーで見られるように、システムのトポロジのすべての要素。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 `ITopologyExecutionResource`  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** concrtrm.h  
  
 **名前空間:** concurrency  
  
##  <a name="getid"></a>Itopologyexecutionresource::getid メソッド  
 この実行リソースのリソース マネージャーの一意の識別子を返します。  
  
```
virtual unsigned int GetId() const = 0;
```  
  
### <a name="return-value"></a>戻り値  
 この実行リソースのリソース マネージャーの一意の識別子。  
  
##  <a name="getnext"></a>Itopologyexecutionresource::getnext メソッド  
 列挙の順番に次の実行リソースへのインターフェイスを返します。  
  
```
virtual ITopologyExecutionResource *GetNext() const = 0;
```  
  
### <a name="return-value"></a>戻り値  
 列挙の順番に次の実行リソースへのインターフェイス。 この実行リソースが属しているノードの列挙の順番でない複数のノードがある場合、このメソッドは値を返しますが`NULL`です。  
  
## <a name="see-also"></a>参照  
 [concurrency 名前空間](concurrency-namespace.md)
