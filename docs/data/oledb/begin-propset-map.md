---
title: "BEGIN_PROPSET_MAP |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: BEGIN_PROPSET_MAP
dev_langs: C++
helpviewer_keywords: BEGIN_PROPSET_MAP macro
ms.assetid: c3a30618-6025-4d49-8688-a171294d2e93
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 24fe8ed41888ab2b3d303a29cd9d004f26b6c6b9
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="beginpropsetmap"></a>BEGIN_PROPSET_MAP
プロパティのセットのマップ エントリを示します。  
  
## <a name="syntax"></a>構文  
  
```  
  
BEGIN_PROPSET_MAP(  
Class   
)  
  
```  
  
#### <a name="parameters"></a>パラメーター  
 *クラス*  
 [in]このプロパティが設定されているクラスを指定します。 プロパティ セットは、次の OLE DB オブジェクトに指定できます。  
  
-   [データ ソース オブジェクト](https://msdn.microsoft.com/en-us/library/ms721278.aspx)  
  
-   [セッション オブジェクト](https://msdn.microsoft.com/en-us/library/ms711572.aspx)  
  
-   [コマンド](https://msdn.microsoft.com/en-us/library/ms724608.aspx)  
  
## <a name="example"></a>例  
 プロパティ セット マップのコード例を次に示します。  
  
 [!code-cpp[NVC_OLEDB_Provider#3](../../data/oledb/codesnippet/cpp/begin-propset-map_1.h)]  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** atldb.h  
  
## <a name="see-also"></a>参照  
 [OLE DB プロバイダー テンプレート用マクロ](../../data/oledb/macros-for-ole-db-provider-templates.md)   
 [OLE DB プロバイダー テンプレート](../../data/oledb/ole-db-provider-templates-cpp.md)   
 [OLE DB プロバイダー テンプレートのアーキテクチャ](../../data/oledb/ole-db-provider-template-architecture.md)   
 [OLE DB プロバイダーの作成](../../data/oledb/creating-an-ole-db-provider.md)