---
title: "BEGIN_PROVIDER_COLUMN_MAP |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: BEGIN_PROVIDER_COLUMN_MAP
dev_langs: C++
helpviewer_keywords: BEGIN_PROVIDER_COLUMN_MAP macro
ms.assetid: 506b8c0f-6be9-4c97-ba81-c4b7f7d428fa
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 05b70429c127927c7b436980f573efedee14707e
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="beginprovidercolumnmap"></a>BEGIN_PROVIDER_COLUMN_MAP
プロバイダーの列マップ エントリの先頭をマークします。  
  
## <a name="syntax"></a>構文  
  
```  
  
BEGIN_PROVIDER_COLUMN_MAP(  
theClass   
)  
  
```  
  
#### <a name="parameters"></a>パラメーター  
 `theClass`  
 [in]このマップが属するクラスの名前。  
  
## <a name="example"></a>例  
 プロバイダーの列マップのコード例を次に示します。  
  
 [!code-cpp[NVC_OLEDB_Provider#4](../../data/oledb/codesnippet/cpp/begin-provider-column-map_1.h)]  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** atldb.h  
  
## <a name="see-also"></a>参照  
 [OLE DB プロバイダー テンプレート用マクロ](../../data/oledb/macros-for-ole-db-provider-templates.md)   
 [OLE DB プロバイダー テンプレート](../../data/oledb/ole-db-provider-templates-cpp.md)   
 [OLE DB プロバイダー テンプレートのアーキテクチャ](../../data/oledb/ole-db-provider-template-architecture.md)   
 [OLE DB プロバイダーの作成](../../data/oledb/creating-an-ole-db-provider.md)