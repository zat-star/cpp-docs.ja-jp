---
title: "PROPERTY_INFO_ENTRY |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: PROPERTY_INFO_ENTRY
dev_langs: C++
helpviewer_keywords: PROPERTY_INFO_ENTRY macro
ms.assetid: f7bd23d6-52b4-4d6a-aa9a-1fca9834c8dc
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 8b5193748f7a4f59abb8806e3d09bf0c77274b89
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="propertyinfoentry"></a>PROPERTY_INFO_ENTRY
プロパティ セットの特定のプロパティを表します。  
  
## <a name="syntax"></a>構文  
  
```  
  
PROPERTY_INFO_ENTRY(  
dwPropID   
)  
  
```  
  
#### <a name="parameters"></a>パラメーター  
 *dwPropID*  
 [入力] プロパティ セット GUID と組み合わせて使用してプロパティを特定する [DBPROPID](https://msdn.microsoft.com/en-us/library/ms723882.aspx) 値。  
  
## <a name="remarks"></a>コメント  
 このマクロは、 `DWORD` 型のプロパティ値を、ATLDB.H で定義された既定値に設定します。 選択した値にプロパティを設定するには、 [PROPERTY_INFO_ENTRY_VALUE](../../data/oledb/property-info-entry-value.md)を使用します。 プロパティの [VARTYPE](http://msdn.microsoft.com/en-us/317b911b-1805-402d-a9cb-159546bc88b4) と [DBPROPFLAGS](https://msdn.microsoft.com/en-us/library/ms724342.aspx) を同時に設定するには、 [PROPERTY_INFO_ENTRY_EX](../../data/oledb/property-info-entry-ex.md)を使用します。  
  
## <a name="example"></a>例  
 「 [BEGIN_PROPSET_MAP](../../data/oledb/begin-propset-map.md)」を参照してください。  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** atldb.h  
  
## <a name="see-also"></a>参照  
 [OLE DB プロバイダー テンプレート用マクロ](../../data/oledb/macros-for-ole-db-provider-templates.md)   
 [OLE DB プロバイダー テンプレート](../../data/oledb/ole-db-provider-templates-cpp.md)   
 [OLE DB プロバイダー テンプレートのアーキテクチャ](../../data/oledb/ole-db-provider-template-architecture.md)   
 [OLE DB プロバイダーの作成](../../data/oledb/creating-an-ole-db-provider.md)