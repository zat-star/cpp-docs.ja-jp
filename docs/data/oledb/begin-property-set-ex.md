---
title: "BEGIN_PROPERTY_SET_EX |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: BEGIN_PROPERTY_SET_EX
dev_langs: C++
helpviewer_keywords: BEGIN_PROPERTY_SET_EX macro
ms.assetid: c95e7fab-edce-47b8-b282-200e53a2ea8a
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: ede0dac08233d82decb23064e47b61cbd9a05da1
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="beginpropertysetex"></a>BEGIN_PROPERTY_SET_EX
プロパティのセットのプロパティの先頭のマークは、マップを設定します。  
  
## <a name="syntax"></a>構文  
  
```  
  
BEGIN_PROPERTY_SET_EX(  
guid  
, flags )  
```  
  
#### <a name="parameters"></a>パラメーター  
 `guid`  
 [in]プロパティの GUID です。  
  
 `flags`  
 [in]**UPROPSET_HIDDEN**を公開したくない任意のプロパティ セットまたは**UPROPSET_PASSTHROUGH**プロバイダーのスコープ外で定義されたプロパティを公開するプロバイダー。  
  
## <a name="example"></a>例  
 「 [BEGIN_PROPSET_MAP](../../data/oledb/begin-propset-map.md)」を参照してください。  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** atldb.h  
  
## <a name="see-also"></a>参照  
 [OLE DB プロバイダー テンプレート用マクロ](../../data/oledb/macros-for-ole-db-provider-templates.md)   
 [OLE DB プロバイダー テンプレート](../../data/oledb/ole-db-provider-templates-cpp.md)   
 [OLE DB プロバイダー テンプレートのアーキテクチャ](../../data/oledb/ole-db-provider-template-architecture.md)   
 [OLE DB プロバイダーの作成](../../data/oledb/creating-an-ole-db-provider.md)