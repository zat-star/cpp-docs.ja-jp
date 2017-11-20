---
title: "Irowsetlocateimpl::compare |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- ATL.IRowsetLocateImpl.Compare
- IRowsetLocateImpl::Compare
- IRowsetLocateImpl.Compare
- ATL::IRowsetLocateImpl::Compare
dev_langs: C++
helpviewer_keywords: Compare method
ms.assetid: 6f84052c-c68c-480a-982f-03748faa7d5d
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 2dba219ef2b2e0747d800d45950217e220ab1449
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="irowsetlocateimplcompare"></a>IRowsetLocateImpl::Compare
2 つのブックマークを比較します。  
  
## <a name="syntax"></a>構文  
  
```  
  
      STDMETHOD ( Compare )(  
   HCHAPTER /* hReserved */,  
   DBBKMARK cbBookmark1,  
   const BYTE* pBookmark1,  
   DBBKMARK cbBookmark2,  
   const BYTE* pBookmark2,  
   DBCOMPARE* pComparison   
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 参照してください[IRowsetLocate::Compare](https://msdn.microsoft.com/en-us/library/ms709539.aspx)で、 *OLE DB プログラマーズ リファレンス*です。  
  
## <a name="remarks"></a>コメント  
 いずれか、それらのブックマークは、標準 OLE DB で定義された[標準ブックマーク](https://msdn.microsoft.com/en-us/library/ms712954.aspx)(**DBBMK_FIRST**、 **DBBMK_LAST**、または**一方**)。 返される値`pComparison`2 つのブックマーク間の関係を示します。  
  
-   **DBCOMPARE_LT** (`cbBookmark1`する前に`cbBookmark2`)。  
  
-   **DBCOMPARE_EQ** (`cbBookmark1`と等しい`cbBookmark2`)。  
  
-   **DBCOMPARE_GT** (`cbBookmark1`後`cbBookmark2`)。  
  
-   **DBCOMPARE_NE** (ブックマークは等しいと順序が付いていません)。  
  
-   **DBCOMPARE_NOTCOMPARABLE** (ブックマークは比較できません)。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** atldb.h  
  
## <a name="see-also"></a>関連項目  
 [IRowsetLocateImpl クラス](../../data/oledb/irowsetlocateimpl-class.md)