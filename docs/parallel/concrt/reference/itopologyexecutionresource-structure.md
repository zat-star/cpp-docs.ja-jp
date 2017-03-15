---
title: "ITopologyExecutionResource 構造体 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- concrtrm/concurrency::ITopologyExecutionResource
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
translationtype: Machine Translation
ms.sourcegitcommit: fa774c7f025b581d65c28d65d83e22ff2d798230
ms.openlocfilehash: cc54beb4790c9d2ea5bfcb2c8ffd4bca7dca399e
ms.lasthandoff: 02/24/2017

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
|[Itopologyexecutionresource::getid メソッド](#getid)|この実行リソースのリソース マネージャーの一意の識別子を返します。|  
|[Itopologyexecutionresource::getnext メソッド](#getnext)|列挙の順番に次の実行リソースへのインターフェイスを返します。|  
  
## <a name="remarks"></a>コメント  
 このインターフェイスは、リソース マネージャーで見られるように、システムのトポロジーを順番に通常使用されます。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 `ITopologyExecutionResource`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** concrtrm.h  
  
 **名前空間:** concurrency  
  
##  <a name="a-namegetida--itopologyexecutionresourcegetid-method"></a><a name="getid"></a>Itopologyexecutionresource::getid メソッド  
 この実行リソースのリソース マネージャーの一意の識別子を返します。  
  
```
virtual unsigned int GetId() const = 0;
```  
  
### <a name="return-value"></a>戻り値  
 この実行リソースのリソース マネージャーの一意の識別子。  
  
##  <a name="a-namegetnexta--itopologyexecutionresourcegetnext-method"></a><a name="getnext"></a>Itopologyexecutionresource::getnext メソッド  
 列挙の順番に次の実行リソースへのインターフェイスを返します。  
  
```
virtual ITopologyExecutionResource *GetNext() const = 0;
```  
  
### <a name="return-value"></a>戻り値  
 列挙の順番に次の実行リソースへのインターフェイス。 この実行リソースが属しているノードの列挙の順番にノードがそれ以上がある場合は、このメソッドは値を返します`NULL`します。  
  
## <a name="see-also"></a>関連項目  
 [同時実行 Namespace](concurrency-namespace.md)

