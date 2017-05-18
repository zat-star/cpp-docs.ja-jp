---
title: "ITopologyExecutionResource 構造体 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- ITopologyExecutionResource
- CONCRTRM/concurrency::ITopologyExecutionResource
- CONCRTRM/concurrency::ITopologyExecutionResource::ITopologyExecutionResource::GetId
- CONCRTRM/concurrency::ITopologyExecutionResource::ITopologyExecutionResource::GetNext
dev_langs:
- C++
helpviewer_keywords:
- ITopologyExecutionResource structure
ms.assetid: e36756f7-4cd9-4fa6-ba60-23fea58ef2bf
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 5faef5bd1be6cc02d6614a6f6193c74167a8ff23
ms.openlocfilehash: d9671dbf84a1104bc3b6f3a6f9d383aac167759c
ms.contentlocale: ja-jp
ms.lasthandoff: 03/17/2017

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
 このインターフェイスは、リソース マネージャーで見られるように、システムのトポロジーを順番に通常使用されます。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 `ITopologyExecutionResource`  
  
## <a name="requirements"></a>要件  
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
 列挙の順番に次の実行リソースへのインターフェイス。 この実行リソースが属しているノードの列挙の順番にノードがそれ以上がある場合は、このメソッドは値を返します`NULL`します。  
  
## <a name="see-also"></a>関連項目  
 [concurrency 名前空間](concurrency-namespace.md)

